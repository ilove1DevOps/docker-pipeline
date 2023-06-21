pipeline {
    agent any {
        stage('Build') {
            steps {
                // Perform test steps here
                sh 'sudo usermode -aG docker $USER'
                sh 'sudo reboot'
                sh 'docker build -t piyushdhir121:i1 .'
            }
        }
        }
}

