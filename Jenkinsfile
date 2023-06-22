pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                sh 'docker build -t piyushdhir121:i1 .'
            }
        }

        stage('Push to Docker Hub') {
            steps {
                sh 'docker login -u docker login -u=abbbb -p=ldo23825@omeie.com'
                sh 'docker push piyushdhir121:i1 '

            }
        }
    }
}
