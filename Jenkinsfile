pipeline {
    agent any
    environment {     
    DOCKERHUB_CREDENTIALS= credentials('dockerhub')     
} 
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t piyushdhir121:i1 .'
            }
        }

        stage('Push to Docker Hub') {
            steps {
                sh 'docker login -u docker login -u=$DOCKERHUB_CREDENTIALS --password-stdin'
                sh 'docker push piyushdhir121:i1 '

            }
        }
    }
}
