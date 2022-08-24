pipeline {
    agent {
        docker {
            image 'node:alpine' 
            args '--name=cnode -p 3000:3000' 
        }
    }

    environment {
        CI = 'true'
    }

    stages {
        stage('Get Path') { 
            steps {
                sh 'pwd' 
            }
        }
        stage('Build') { 
            steps {
                sh 'node -v' 
                sh 'docker ps'
            }
        }
    }
}
