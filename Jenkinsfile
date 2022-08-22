pipeline {
    agent {
        docker {
            image 'node:alpine' 
            args '-p 3000:3000' 
        }
    }
    stages {
        stage('Get Path') { 
            steps {
                sh 'pwd' 
            }
        }
        stage('Build') { 
            steps {
                nodejs() {
                    sh 'npm install'
                }
            }
        }
    }
}