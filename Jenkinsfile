pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout([
                    $class: 'GitSCM',
                    branches: [[name: '*/main']],
                    userRemoteConfigs: [[url: 'https://github.com/mjhamb/couseraMod5_assignment.git']]
                ])
            }
        }
        stage('Build') {
            steps {
                sh 'npm install'  // Use the appropriate build command
            }
        }
        stage('Test') {
            steps {
                sh 'npm test'  // Use the appropriate test command
            }
        }
        stage('Deploy') {
            steps {
                sh 'rsync -avz ./dist/ user@server:/path/to/deployment/directory'
            }
        }
    }
    post {
        success {
            echo 'Build successful! Deploy your application.'
        }
        failure {
            echo 'Build failed. Check your code and build process.'
        }
    }
}
