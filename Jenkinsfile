pipeline {
    agent any
    stages {
        stage ('Jenkins') {
            steps {
                sh "echo 'This is the master branch'"
                sh "cat ./README.md"
                sh "pwd"
                sh "ls"
                sh "git rev-parse --short HEAD"
            }
        }
    }
}