pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image "node:18-alpine"
                    reuseNode true
                }
            }
            steps {
                sh '''
                    echo "Checking Docker version..."
                    docker --version
                    ls -la
                    node --version
                    npm --version
                    npm ci
                    npm run build
                '''
            }
        }
    }
}
