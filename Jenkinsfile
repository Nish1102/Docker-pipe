pipeline {
    agent any

    stages {
        stage('Run Nginx Container') {
            steps {
                script {
                    docker.image('nginx:alpine').withRun('-p 8080:80 --name nginx-container')
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

