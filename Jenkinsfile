pipeline {
    agent any

    stages {
        stage('Run Nginx Container') {
            steps {
                script {
                    // Use 'pwd' instead of 'echo %CD%' to get the current working directory
                    def currentDir = bat(script: 'pwd', returnStatus: true).trim()

                    echo "Current working directory: ${currentDir}"

                    // Run the Nginx container
                    def nginxImage = docker.image('nginx:alpine')
                    nginxImage.inside("-p 8080:80 --name nginx-container -w ${currentDir}") {
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
