pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    // Checkout code from Git
                    checkout scm

                    // Run the Docker container
                    withDockerContainer(
                        image: 'node:16-alpine',
                        args: '--entrypoint ""', // Override the entrypoint to run commands directly
                        workspaceDir: '/path/to/your/absolute/workspace'
                    ) {
                        // Run your Docker-related commands here
                        sh 'node --version'
                    }
                }
            }
        }
    }
}
