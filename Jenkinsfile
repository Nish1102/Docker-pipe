pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                sh '/usr/bin/docker run node:16-alpine node --version'
            }
        }
    }
}
