pipeline {
    agent any
    stages {
        stage ('Maven build') {
            steps {
                // Use 'tool' step to automatically configure Maven
                tool 'maven3'
                // Execute Maven commands directly
                sh 'mvn clean package'
                // Rename the generated WAR file
                sh 'mv target/myweb*.war target/newapp.war'
            }
        }
        stage ('Docker build') {
            steps {
                // Execute Docker commands directly
                sh 'docker build -t newimage:v1 .'
                // Display Docker images for verification
                sh 'docker images'
            }
        }
    }
}
