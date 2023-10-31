pipeline {
    agent {
        label 'Windows 10'
    }
     // ...
    }
    stages {
        stage('Build') {
            steps {
                // Use the appropriate build command
                bat 'npm install'
            }
        }
        stage('Test') {
            steps {
                // Use the appropriate test command
                bat 'npm test'
            }
        }
        stage('Deploy') {
            steps {
                // Use Windows-compatible command for deployment using robocopy
                bat 'robocopy C:\\path\\to\\your\\workspace\\dist \\\\server\\path\\to\\deployment\\directory /mir'
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

