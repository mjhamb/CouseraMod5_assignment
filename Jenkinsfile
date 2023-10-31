pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/mjhamb/couseraMod5_assignment.git']])
            }
        }
        stage('Build') {
            steps {
                // Build your project (modify the command as needed)
                sh 'npm install'  // Use the appropriate build command
            }
        }
        stage('Test') {
            steps {
                // Run tests (customize this section based on your testing framework)
                sh 'npm test'  // Use the appropriate test command
            }
        }
        stage('Deploy') {
            steps {
                // Deploy your application (customize this section for your deployment process)
                // Example: Copy files to a web server, upload to a hosting service, etc.
                sh 'rsync -avz ./dist/ user@server:/path/to/deployment/directory'
            }
        }
    }
    post {
        success {
            // Define post-build actions for a successful build
            echo 'Build successful! Deploy your application.'
        }
        failure {
            // Define post-build actions for a failed build
            echo 'Build failed. Check your code and build process.'
        }
    }
}
