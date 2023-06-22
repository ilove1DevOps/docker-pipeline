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
                withCredentials([string(credentialsId: 'DockerhubPassword', variable: 'dockerpwd')]) {
                sh 'docker login -u abbbb -p ${dockerpwd}'
                sh 'docker push piyushdhir121:i1 '
}
               

            }
        }
    }
}
