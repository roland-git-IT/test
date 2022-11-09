pipeline {
    agent any
    stages {
        stage ('Jenkins') {
            def GIT_COMMIT = sh "git rev-parse --short HEAD"
            steps {
                sh "echo 'This is the master branch'"
                sh "cat ./README.md"
                sh "pwd"
                sh "ls -a"
                echo env.JOB_NAME
                sh "echo $GIT_COMMIT"
            }
        }
    }
}