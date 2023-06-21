pipeline {
    agent any

    environment {
        DOCKER_HUB_USERNAME = credentials('ldo23825@omeie.com')
        DOCKER_HUB_PASSWORD = credentials('ldo23825@omeie.com')
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/ilove1DevOps/docker-pipeline.git'
            }
        }

        stage('Build and Push Image') {
            steps {
                script {
                    def dockerImage = docker.build("my-docker-image:${env.BUILD_NUMBER}") // Specify your desired image name and tag
                    docker.withRegistry('https://registry.hub.docker.com', 'docker-hub-credentials') {
                        dockerImage.push() // Push the image to Docker Hub
                    }
                }
            }
        }
    }
}
