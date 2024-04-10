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
                script {
                    sh 'npm install' // Install dependencies
                }
            }
        }

        stage('Test') { // Run tests
            steps {
                script {
                    sh 'npm test' // Run tests
                }
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
