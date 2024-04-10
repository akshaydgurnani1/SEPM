pipeline {
    agent any
    
    environment {
        DOCKER_IMAGE = 'your-docker-image-name:latest'
    }
    
    stages {
        stage('Build Docker Container') {
            steps {
                script {
                    // Build Docker container
                    docker.build(DOCKER_IMAGE)
                }
            }
        }
        
        stage('Build Application') {
            steps {
                // Your build steps here
                // For example, if you're building a Node.js application:
                sh 'npm install'  // Install dependencies
                sh 'npm run build'  // Build the application
            }
        }
    }
    
    post {
        always {
            // Clean up steps, notifications, etc.
            // You can include steps to clean up resources, send notifications, etc.
        }
    }
}
