pipeline {
    agent any
    stages {
        def GIT_COMMIT = sh "git rev-parse --short HEAD"
        stage ('Jenkins') {
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