pipeline {
    agent any
    stages {
        stage ('Jenkins') {
            steps {
                sh "echo 'This is the master branch'"
                sh "cat ./README.md"
                sh "pwd"
                sh "ls -a"
                step {
                    GIT_COMMIT = sh (
                        script: 'git rev-parse --short HEAD',
                        returnStdout: true
                    ).trim()
                    echo "Git commit: ${GIT_COMMIT}"
                }
                    echo env.JOB_NAME
                sh "echo $GIT_COMMIT"
            }
        }
    }
}