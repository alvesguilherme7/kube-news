pipeline {
    agent any


    stages {

        stage('Build Docker Image') {
            steps {
                script {
                    dockerapp = docker.build('docker push alvesguilherme7/kubenews:v${env.BUILD_ID}', '-f ./src/Dockerfile ./src')
                }
            }
        }

    }
}