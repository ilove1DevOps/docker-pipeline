pipeline {
    agent docker

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/ilove1DevOps/docker-pipeline.git'
            }
        }
        
        stage('Build') {
            steps {
                sh 'docker build -t myapp .'
            }
        }

        stage('Deploy') {
            steps {
                sh 'docker run -d -p 8080:80 myapp'
            }
        }
    }
}
