pipeline {
    agent any

    stages {
        stage('Build') {
            agent{
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    apk update && apk upgrade  // Update Alpine packages
                    node --version
                    npm --version
                    npm install --update-binary  // Use install as a test alternative to npm ci
                    npm run build


                '''
            }
        }
    }
}
