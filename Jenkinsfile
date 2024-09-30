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
                    export npm_config_cache=/path/to/cache
                    npm ci
                    npm run build
                    ls -la
                '''
            }
        }
    }
}
//sudo chown -R 501:20 /.npm