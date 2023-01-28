pipeline {
    agent any


    stages {

        stage("Build Docker Image") {
            steps {
                script {
                    dockerapp = docker.build("alvesguilherme7/kubenews:${env.BUILD_ID}", "-f ./src/Dockerfile ./src")
                }
            }
        }

    }
}