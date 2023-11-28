pipeline {
    agent {
        label 'docker-agent'
    }
    stages {
        stage('Test') {
            steps {
                sh 'docker run node:16-alpine node --version'
            }
        }
    }
}

