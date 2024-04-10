pipeline {
    agent any

    environment {
        CI = 'true' // Set CI environment variable to true (optional)
        NODEJS_HOME = tool 'nodejs'
    }

    stages {
        stage('Checkout') { // Fetch code from Git repository (optional)
            steps {
                // Replace with your Git checkout command or use a Git plugin
                git branch: 'main', // Replace 'main' with your desired branch (master is also common)
                   url: 'https://github.com/akshaydgurnani1/SEPM.git' // Replace with your Git repository URL
            }
        }

        stage('Build') { // Assuming Node.js project
            steps {
                script { // Use script block for better portability
                    bat 'npm install' // Install dependencies
                    bat 'npm run build' // Build the project
                }
            }
        }

        // Add additional stages for tasks like linting, code coverage, testing, and deployment as needed
    }

    post { // Add post-build actions (optional)
        always {
            echo 'Pipeline execution finished.' // Example notification
        }
    }
}
