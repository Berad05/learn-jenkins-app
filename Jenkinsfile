pipeline {
    agent {
      docker{
        image 'node:18-alpine'
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

        stage('Test'){
          agent {
      docker{
        image 'node:18-alpine'
      }
    }
          steps{
            sh '''
             test -f build/index.html
             npm test
            '''
          }
        }
    }
}