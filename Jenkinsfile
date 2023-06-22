pipeline {
    agent any
    environment {     
        DOCKERHUB_CREDENTIALS= credentials('dockerhub')     
        }
    stages {
        stage('Build') {
            steps {
                // Build steps here
                sh 'docker build -t piyushdhir121:i1 .'
            }
        }

        stage('Docker Login') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'DOCKER_HUB_CREDENTIALS', passwordVariable: 'DOCKER_PASSWORD', usernameVariable: 'DOCKER_USERNAME')]) {
                    sh "echo $DOCKER_PASSWORD | docker login --username $DOCKER_USERNAME --password-stdin"
                }
            }
        }
        
        // Add more stages as needed
        
    }
}
