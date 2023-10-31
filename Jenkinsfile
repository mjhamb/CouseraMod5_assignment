pipeline {
    agent {
        node {
            label 'your-windows-agent-label'
            customWorkspace 'C:\\path\\to\\your\\workspace'
        }
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
                // Use Windows-compatible command for deployment, e.g., xcopy or robocopy
                bat 'xcopy /s C:\\path\\to\\your\\workspace\\dist user@server:/path/to/deployment/directory'
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
