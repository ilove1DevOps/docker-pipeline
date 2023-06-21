pipeline {
    agent {
        docker {
            image 'docker:latest' // Specify the Docker image to use for the Jenkins agent
            args '-v /var/run/docker.sock:/var/run/docker.sock' // Mount the Docker socket inside the container
        }
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/ilove1DevOps/docker-pipeline.git'
            }
        }

        stage('Build') {
            steps {
                script {
                    docker.build('myapp') // Build the Docker image with the tag 'myapp'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    docker.run('-p 8080:80 -d --name myapp-container myapp') // Run the Docker container with the name 'myapp-container'
                }
            }
        }
    }

    post {
        always {
            script {
                docker.image('myapp').push() // Push the Docker image to a registry (if desired)
                docker.image('myapp').remove() // Remove the Docker image from the Jenkins agent
                docker.image('docker:latest').inside {
                    sh 'docker stop myapp-container' // Stop the running container
                    sh 'docker rm myapp-container' // Remove the container
                }
            }
        }
    }
}
