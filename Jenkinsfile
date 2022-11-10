//def branch = env.BRANCH_NAME
//properties([
parameters {
    string(defaultValue: 'ghost', description: 'Ghost in shell', name: 'python')
    string(defaultValue: 'master', description: 'master branch', name: 'branch')
}
//parameters([string(defaultValue: 'master', description: 'master branch', name: 'branch')])
//])
node {
    stage ('scripting') {
        //properties([parameters([string(defaultValue: 'master', description: 'master branch', name: 'branch')])])
        //string(name: 'branch', defaultValue: 'master', description: "This is the production branch")
        def BRANCH = env.BRANCH_NAME
        withCredentials([usernamePassword(credentialsId: 'github_token', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
            git url: 'https://github.com/roland-git-IT/test.git', branch: env.BRANCH_NAME
        }
        GIT_COMMIT = sh (script: 'git rev-parse --short HEAD', returnStdout: true).trim()
        echo "Git commit: ${GIT_COMMIT}"

        echo env.JOB_NAME
        // script {
        //     def JOB = env.JOB_NAME | sh "$(awk -F \"/\" '{print \$1}')"
        // }

        sh """
            echo "$BRANCH"
            echo "${params.branch}"
            echo "${params.python}"
        """
        //echo "${params.python}"
        
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