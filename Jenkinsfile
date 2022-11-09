pipeline {
    agent any
    stages {
        stage ('Jenkins') {
            steps {
                sh "echo 'This is the master branch'"
                sh "cat ./README.md"
                sh "pwd"
                sh "ls -a"
                def GIT_COMMIT = sh "git rev-parse --short HEAD"
                echo env.JOB_NAME
                echo env.GIT_COMMIT
            }
        }
    }
}