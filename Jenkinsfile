pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                }
            } 
            steps {
                sh '''
                    ls -la
                    node --version
                    npm --version
                    npm ci
                    npm cache clean --force
                    npm run build
                    ls -la
                '''
            }
        }
    }
}
//sudo chown -R 501:20 /.npm