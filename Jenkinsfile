pipeline {
    agent any

    // stages {
    //         stage('Checkout') {
    //             steps {
    //             // Perform build steps here
    //             sh 'git branch: 'main', url: 'https://github.com/ilove1DevOps/docker-pipeline.git''
    //         }
    //     }

        stage('Build') {
            steps {
                // Perform test steps here
                sh 'docker build -t piyushdhir121:i1 .'
            }
        }
        }
    }
}
