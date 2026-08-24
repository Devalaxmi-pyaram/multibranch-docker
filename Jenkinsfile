pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t image1 .'
            }
        }
        stage ("Tag") {
            steps {
                sh 'docker tag image1 dpyaram/paytm:bank'
            }
        }
        stage('Push') {
            steps {
                script {
                   withDockerRegistry(credentialsId: 'docker-password', url: 'https://hub.docker.com/repositories/dpyaram') {
    // some block
                          
                    }
                }
            }
        }
        
        stage ("Deploy") {
            steps {
                sh 'docker run -itd --name bank-app -p 1111:80 dpyaram/paytm:bank'
            }
        }
    }
}
