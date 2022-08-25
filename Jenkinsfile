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
            mail bcc: '', body: 'Hello Pipeline!', cc: 'emmerson.oliveira@rotatransportes.com.br', from: 'sroliver201923@gmail.com', replyTo: '', subject: 'Jenkins', to: 'emmerson.oliveira@rotatransportes.com.br'
            emailext body: 'A Test EMail', recipientProviders: [[$class: 'DevelopersRecipientProvider'], [$class: 'RequesterRecipientProvider']], subject: 'Test'
        }
    }
}
