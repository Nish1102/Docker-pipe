pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                bat '%DOCKER_HOME% run node:16-alpine node --version'
            }
        }
    }
}
