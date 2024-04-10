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

        
    }

    post {
        always {
            echo 'Pipeline execution finished.'
        }
    }
}
