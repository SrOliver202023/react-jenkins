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
                sh 'whoami' 
                sh '$user' 
            }
        }
        stage('Build') { 
            steps {
                sh 'npm install' 
            }
        }
    }
}