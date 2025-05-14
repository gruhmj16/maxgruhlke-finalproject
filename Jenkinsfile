pipeline {
    agent any
    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/gruhmj16/maxgruhlke-finalproject.git'
            }
        }
        stage('Deploy to S3') {
            steps {
                withAWS(region: 'us-east-1', credentials: 'd0fa57dc-3632-4193-8942-6c5fb04bac6f') {
                    sh 'aws s3 cp . s3://maxgruhlke-finalproject/ --recursive --exclude ".git/*"'
                }
            }
        }
    }
}
