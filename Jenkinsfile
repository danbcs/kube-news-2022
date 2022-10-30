pipeline {
    agent any

    stages {
        stage ('Build Docker Image') {
            steps {
                script {
                    dokerapp = docker.built("danbcs/kubenews:${env.BUILD_ID}", '-f ./src/Dockerfile ./src')
                }
            }
        }
    }
}