/* Requires the Docker Pipeline plugin */
pipeline {
    agent { docker { image 'node:20.9.0-alpine3.18' } }
    stages {
        stage('Build') {
            steps {
                sh 'node --version'
            }
        }
    }
}
