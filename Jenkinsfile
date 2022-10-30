pipeline {
    agent any

    stages {
        stage ('Build Docker Image') {
            steps {
                script {
                    dokerapp = docker.build("danbcs/kube-news:${env.BUILD_ID}", '-f ./src/Dockerfile ./src')
                }
            }
        }
    }
    stages {
        stage ('Push Docker Image') {
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub')
                    dokerapp.push('latest')
                    dokerapp.push("${env.BUILD_ID}")
                }
            }
        }
    }
}