pipeline {
    agent any
    
    environment {
        CI = 'true' // Set CI environment variable to true
    }

    stages {
        stage('Checkout') { // Fetch code from Git repository
            steps {
                git branch: 'main', // Replace 'main' with your desired branch (master is also common)
                   url: 'https://github.com/akshaydgurnani1/jenkins.git' // Replace with your Git repository URL
            }
        }

        stage('Build') { // Assuming Node.js project
            steps {
                bat 'npm install' // Use bat step for Windows
            }
        }

        stage('Test') { // Run tests
            steps {
                bat 'npm test' // Use bat step for Windows
            }
        }

        // Add additional stages for tasks like linting, code coverage, and deployment as needed
    }

    post { // Add post-build actions (optional)
        always {
            echo 'Pipeline execution finished.' // Example notification
        }
    }
}
