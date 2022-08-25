pipeline {
    agent {
        docker {
            image 'node:alpine' 
            args '--name=react-jenkins -p 4173:4173' 
        }
    }

    environment {
        CI = 'true'
        HOME = '.'
    }

    stages {
        stage('Get Path') { 
            steps {
                sh 'pwd' 
            }
        }
        stage('Get Ip') { 
            steps {
                sh 'hostname -i' 
            }
        }
        stage('Packages') { 
            steps {
                sh "npm install"
            }
        }
        stage('Build') { 
            steps {
                sh "npm run build"
            }
        }

    }

    post {
        always {
            emailext body: 'A Test EMail', recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']], subject: 'Test'
        }
    }
}
