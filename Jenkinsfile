pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'docker build -t image3 .'
            }
        }
        stage ("Tag") {
            steps {
                sh 'docker tag image3 dpyaram/paytm:movie'
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
                sh 'docker run -itd --name movie-app -p 3333:80 dpyaram/paytm:movie'
            }
        }
    }
}
