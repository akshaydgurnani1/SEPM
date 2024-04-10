pipeline {
    agent any
      environment {
        DOCKER_IMAGE = 'akshay091203:latest'
    }
    
    stages {
        stage('Build Docker Container') {
            steps {
                script {
                    // Navigate to the directory containing the Dockerfile
                    dir('path/to/Dockerfile/directory') {
                        // Build Docker container
                        docker.build(DOCKER_IMAGE)
                    }
                }
            }
        }
    }
  
    
    stages {
        stage('Build') {
            steps {
                // Run npm start command or any other build steps
                bat 'start npm start'
            }
        }
        
        
        
        // Define additional stages here
    }
    
}