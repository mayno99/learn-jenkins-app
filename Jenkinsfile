pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    args '-u root'  
                }
            }
            steps {
                sh '''
                    apk update && apk upgrade  
                    node --version
                    npm --version
                    npm install --update-binary
                '''
            }
        }
    }
}
