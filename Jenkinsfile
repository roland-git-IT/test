pipeline {
    agent any
    stages {
        stage ('Jenkins') {
            steps {
                sh "echo 'This is the master branch'"
                sh "cat ./README.md"
                sh "pwd"
                sh "ls -a"
                echo env.JOB_NAME
                def COMMIT = sh "git rev-parse --short HEAD"
                sh "echo $GIT_COMMIT"
            }
        }
    }
}