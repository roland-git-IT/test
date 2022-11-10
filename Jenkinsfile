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

node {
    stage ('scripting') {
        COMMIT = env.GIT_COMMIT
        echo env.GIT_COMMIT
        sh "echo ${COMMIT}"
    }
}