pipeline {
    agent none
    stages {
        
         stage('Checkout SCM') {
            agent {
                label 'master'
            }
            steps {
                checkout scm
            }
        }
        
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
              
                sh 'docker build . -t yusufluai/landingpage:$BUILD_NUMBER'
                sh 'docker push yusufluai/landingpage:$BUILD_NUMBER'
            }
        }
    }
}
