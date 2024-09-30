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
                    sudo ls -la
                    sudo node --version
                    sudo npm --version
                    sudo npm ci
                    sudo npm run build
                    sudo ls -la
                '''
            }
        }
    }
}
//sudo chown -R 501:20 /.npm