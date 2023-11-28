pipeline {
    agent any

    tools {
        // Define the Docker installation
        dockerTool 'docker'
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    def dockerImage = docker.build('noteimg:latest', '.')
                }
            }
        }

        // ... (other stages)
    }

    post {
        // ... (post actions)
    }
}

