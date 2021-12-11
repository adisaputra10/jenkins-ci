pipeline {
    agent none
    stages {
        stage('Unit Testing') {
            agent {
                docker { image 'node:14-alpine' }
            }
            steps {
                sh 'node --version'
            }
        }
        stage('Build ') {
              agent {
                label 'master'
            }
            steps {
              
                sh 'docker build . -t image:$BUILD_NUMBER'
            }
        }
    }
}
