pipeline {
    agent any

    stages {
        stage('Check Tools') {
            steps {
                sh 'node -v'
                sh 'npm -v'
            }
        }

        stage('Install') {
            steps {
                sh 'npm ci'
            }
        }

        stage('Test') {
            steps {
                sh 'npm test'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                    sudo mkdir -p /var/www/railway-ticket-application
                    sudo rm -rf /var/www/railway-ticket-application/*
                    sudo cp -r dist/. /var/www/railway-ticket-application/
                '''
            }
        }
    }

    post {
        success {
            echo 'SUCCESS: Your React application is deployed!'
        }

        failure {
            echo 'FAILED: Check the Jenkins console output.'
        }
    }
}

