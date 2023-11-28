pipeline {
    agent any
    environment {
        DOCKER_PATH = 'C:\\Program Files\\Docker\\Docker\\resources\\bin\\docker.exe'
    }
    stages {
        stage('Test') {
            steps {
                bat "\"${DOCKER_PATH}\" run node:16-alpine node --version"
            }
        }
    }
}
