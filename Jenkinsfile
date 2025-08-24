pipeline {
    agent {
      docker{
        image 'node18:18-alpine'
      }
    }

    stages {
        stage('Build') {
            steps {
                sh '''
                  ls -la
                  npm --version
                  node --version
                  npm ci
                  npm run build
                  ls -la
                '''
            }
        }
    }
}