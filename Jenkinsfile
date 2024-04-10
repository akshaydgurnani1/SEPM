pipeline {
    agent any
    
    environment {
        CI = 'true' // Set CI environment variable to true
    }

    stages {
        stage('Checkout') { // Fetch code from Git repository
            steps {
                // Use 'checkout' instead of 'git' step for better cross-platform compatibility
                checkout([$class: 'GitSCM', 
                          branches: [[name: 'main']], 
                          userRemoteConfigs: [[url: 'https://github.com/akshaydgurnani1/jenkins.git']]])
            }
        }

        stage('Build') { // Assuming Node.js project
            steps {
                // Use NodeJS plugin to run npm commands
                nodejs(nodeJSInstallationName: 'nodejs', configId: null) {
                    sh 'npm build run'
                }
            }
        }

        stage('Deploy') { 
            steps {
                sh 'npm start'
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
