def branch = env.BRANCH_NAME
node {
    stage ('scripting') {
        withCredentials([usernamePassword(credentialsId: 'github_token', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
            git url: 'https://github.com/roland-git-IT/test.git', branch: '${branch}'
        }
        COMMIT = env.GIT_COMMIT
        echo env.GIT_COMMIT
        sh "echo ${COMMIT}"
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