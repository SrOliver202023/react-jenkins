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
                nodejs(nodeJSInstallationName: 'Node 16.15.0', configId: '<config-file-provider-id>') {
                    sh 'npm install'
                }
            }
        }
    }
}