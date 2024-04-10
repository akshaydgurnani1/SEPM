pipeline {
    agent any
    
    environment {
        NODEJS_HOME = tool 'nodejs' // This assumes you've configured NodeJS tool in Jenkins
    }
    
    stages {
        stage('Test') {
            steps {
                // Install npm packages locally
                sh "${NODEJS_HOME}/bin/npm install html-validator-cli"
                // You can also specify specific versions or other packages here
            }
        }
        stage('Deployment') {
            steps {
                script {
                    // Enclose shell steps in curly braces
                    sh 'sudo cp /akshaydgurnani1/SEPM'
                    sh 'sudo systemctl restart nginx'
                }
            }
        }
    }
}
