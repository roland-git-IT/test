pipeline {
    agent any
    stages {
        stage ('Jenkins') {
            sh "echo 'This is the master branch'"
            sh "cat ./README.md"
            sh "pwd"
            sh "ls -a"
            echo env.JOB_NAME
            sh "echo $GIT_COMMIT"
        }
    }
}