pipeline {
    agent any

    environment {
        CI = 'true' // Set CI environment variable to true
    }

    stages {
        stage('Checkout') { // Add this stage to fetch code
            steps {
                // Replace with your Git checkout command or use a Git plugin
                git branch: 'main', // Replace 'master' with your desired branch
                   url: 'https://github.com/akshaydgurnani1/jenkins.git' // Replace with your Git repository URL
            }
        }

        stage('Build') { // Assuming Node.js project
            steps {
                script { // Use script block for better portability (works with both Windows and Linux)
                    sh 'npm install' // Install dependencies
                }
            }
        }

        stage('Test') {
            steps {
                script { // Use script block for portability
                    sh 'npm test' // Run tests
                }
            }
        }

        // Add additional stages for tasks like linting, code coverage, and deployment as needed
    }

    post { // Add post-build actions (optional)
        always {
            // Cleanup tasks, notifications, etc. here
            echo 'Pipeline execution finished.' // Example notification
        }
    }
}
