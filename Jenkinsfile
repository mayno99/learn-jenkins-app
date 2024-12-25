pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-buster'  // Using Debian-based image
                    args '-u root'  // Run as root inside the Docker container
                }
            }
            steps {
                sh '''
                    apt-get update && apt-get install -y ca-certificates && update-ca-certificates
                    node --version
                    npm --version
                    npm install --update-binary
                '''
            }
        }
    }
}
