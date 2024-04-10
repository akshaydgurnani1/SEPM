pipeline {
    agent any
    
    environment {
        DOCKER_IMAGE = 'akshay091203:latest'
    }
    
    stages {
        stage('Build') {
            steps {
                // Run npm start command or any other build steps
                bat 'start npm start'
            }
        }
        
        stage('Build Docker Container') {
            steps {
                script {
                    // Build Docker container
                    docker.build(DOCKER_IMAGE)
                }
            }
        }
        
        // Define additional stages here
    }
    
}