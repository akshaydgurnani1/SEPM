pipeline {
    agent any
       environment {
        CI = 'true' // Set CI environment variable to true
    }
    
    stages {
        stage('Build') {
            steps {
                // Run npm start command or any other build steps
                bat 'npm start'
            }
        }
        
        stage('Test') {
            steps {
                // Run tests for your application
                // Replace the following command with the actual command to run your tests
                bat 'npm test'
            }
        }
        
        // Define additional stages here
    }
}
