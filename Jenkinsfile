pipeline {
    agent any

    environment {
        CI = 'true' // Set CI environment variable to true (optional)
        NODEJS_HOME = tool 'nodejs'
        SSH_KEY = credentials('key-04a4e34b1068418ff') // Reference to Jenkins SSH credentials
        EC2_INSTANCE = '18.212.60.212' // Replace with your EC2 instance IP or hostname
        SSH_USER = 'akshaydgurnani' // Replace with your EC2 instance SSH user
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
                    // SSH into the EC2 instance and transfer files
                    sshagent(credentials: ['key-04a4e34b1068418ff']) {
                    sh "scp -i ${SSH_KEY} -r ./SEPM ${SSH_USER}@${EC2_INSTANCE}:/home/akshaydgurnani                    }
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    bat 'npm test'
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
