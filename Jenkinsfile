//def branch = env.BRANCH_NAME
node {
    stage ('scripting') {
        //string(name: 'branch', defaultValue: 'master', description: "This is the production branch")
        def BRANCH = env.BRANCH_NAME
        withCredentials([usernamePassword(credentialsId: 'github_token', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
            git url: 'https://github.com/roland-git-IT/test.git', branch: env.BRANCH_NAME
        }
        GIT_COMMIT = sh (script: 'git rev-parse --short HEAD', returnStdout: true).trim()
        echo "Git commit: ${GIT_COMMIT}"

        echo env.JOB_NAME
        def JOB = env.JOB_NAME | script: "awk -F\"/\" '{print \$1}'"
        sh """
            echo "$BRANCH"
        """
        //COMMIT = env.GIT_COMMIT
        //echo env.GIT_COMMIT
        //sh "echo ${COMMIT}"
    }
}

pipeline {
    agent any
    stages {
        stage ('Jenkins') {
            steps {
                sh "echo 'This is the master branch'"
                sh "cat ./README.md"
                sh "pwd"
                sh "ls -a"
                echo env.GIT_COMMIT
                echo env.JOB_NAME
            }
        }
    }
}