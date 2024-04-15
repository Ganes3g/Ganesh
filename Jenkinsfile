pipeline {
    agent any
    stages {
        stage ('Build') {
            steps {
                script {
                        sh 'npm install'
                }
        stage ('Docker build') {
            steps {
                script {
                    sh 'docker build -t newimage:v1 .'
                    sh 'docker images'
                    sh 'docker run -itd --name containername -P newimage:v1'
                    sh 'docker ps'
                }
            }
        }
        
            }
        }
    }
}
