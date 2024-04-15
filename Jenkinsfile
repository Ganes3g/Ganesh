pipeline {
    agent any
    stages  {
        stage ('Maven build') {
            steps {
                scripts {
                    def mvnHome= tool name:'maven3',type:'maven'
                    sh "${mvnHome}/bin/mvn clean package"
                    sh 'mv target/myweb*.war target/newapp.war'
                }
            }
        }
        stage ('Docker build'){
            steps {
                scripts {
                    sh 'docker build -t newimage:v1 .'
                    sh 'docker images'
                }
            }
        }
    }
}
