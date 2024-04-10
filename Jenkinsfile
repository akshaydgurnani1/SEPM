pipeline {
    agent any
    
    environment {
        DOCKER_IMAGE = 'akshay091203:latest'
    }
        stages {
        stage('Build') {
            steps {
                sh 'npm start'
            }
        }
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
    }
}