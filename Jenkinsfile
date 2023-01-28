pipeline {
    agent any


    stages {

        stage("Build Docker Image") {
            steps {
                script {
                    dockerapp = docker.build("alvesguilherme7/kubenews:v${env.BUILD_ID}", "-f ./src/Dockerfile ./src")
                }
            }
        }

        stage("Push Docker Image"){
            steps {
                script {
                    docker.withRegistry("https://registry.hub.docker.com", 'dockerhub') {
                        dockerapp.push("latest")
                        dockerapp.push("v${env.BUILD_ID}")
                    }
                }
            }
        }

    }
}