pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    def dockerImage = docker.build('noteimg:latest:latest', '.')
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    def dockerContainer = docker.image('noteimg:latest:latest').run('-p 8080:80')
                }
            }
        }

        stage('Test') {
            steps {
                // Add your testing steps here
                echo 'Running tests...'
            }
        }

        stage('Deploy') {
            steps {
                // Add your deployment steps here
                echo 'Deploying...'
            }
        }
    }

    post {
        success {
            echo 'Pipeline succeeded! Clean up resources if needed.'
        }
        failure {
            echo 'Pipeline failed! Take necessary actions.'
        }
    }
}
