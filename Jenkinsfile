pipeline {
    agent any

    environment {
        CI = 'true' // Set CI environment variable to true (optional)
        NODEJS_HOME = tool 'nodejs'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                   url: 'https://github.com/akshaydgurnani1/SEPM.git'
            }
        }

        stage('Build') {
            steps {
                script {
                    bat 'npm install'
                    bat 'npm run build'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Add your deployment script here
                    // For example, if deploying to a server via SSH:
                    // bat 'ssh user@server "deploy-script.sh"'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Add your testing script here
                    // For example, if running tests with Jest:
                    // bat 'npm test'
                }
            }
        }
    }

    post {
        always {
            echo 'Pipeline execution finished.'
        }
    }
}
