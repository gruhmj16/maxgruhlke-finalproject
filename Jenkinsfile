pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
                sh 'npm run build'
                sh 'ls'
                sh 'cd build'
                sh 'ls'
            }
        }
        stage('S3 Upload') {
            steps {
                withAWS(region: 'us-east-1', credentials: 'd0fa57dc-3632-4193-8942-6c5fb04bac6f') {
                    sh 'ls -la build'
                    sh 'aws s3 cp build s3://maxgruhlke-finalproject/ --recursive'
                }
            }
        }
    }
}
