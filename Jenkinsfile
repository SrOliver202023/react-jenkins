pipeline {
    agent {
        docker {
            image 'node:lts-bullseye-slim' 
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
                sh 'npm install' 
            }
        }
    }
}