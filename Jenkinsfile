pipeline {
    agent any

    stages {
        stage('Run Nginx Container') {
            steps {
                script {
                    def nginxImage = docker.image('nginx:alpine')
                    nginxImage.inside('-p 8080:80 --name nginx-container') {
                        // Add any commands you want to run inside the container if needed
                    }
                }
            }
        }
    }

    post {
        success {
            script {
                echo 'Nginx container is running successfully!'
            }
        }

        failure {
            script {
                echo 'Failed to run Nginx container!'
            }
        }
    }
}
