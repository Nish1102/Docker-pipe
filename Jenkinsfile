pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                  git 'https://github.com/nish1102/Docker-pipe.git'
            }
        }

        stage('Build Nginx Docker Image') {
            steps {
                script {
                    def dockerImage = docker.build('nginx-alpine:latest', '--file Dockerfile.nginx .')
                }
            }
        }

        stage('Run Nginx Container') {
            steps {
                script {
                    docker.image('nginx-alpine:latest').withRun('-p 8080:80 --name nginx-container')
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    sh 'echo "Deployment steps go here"'
                    // Add any additional deployment steps you may need
                }
            }
        }
    }

    post {
        success {
            script {
                echo 'Build and deployment successful!'
            }
        }

        failure {
            script {
                echo 'Build or deployment failed!'
            }
        }
    }
}
