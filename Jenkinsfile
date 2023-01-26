pipeline {
    agent any

    stages {

        stage ('Build Docker Image') {
            steps {
                script {
                    dockerapp = docker.build("ledomartinelli/kube-news:${env.Build_ID}", '-f ./src/Dockerfile ./src')
                }
            }
        }

        sateg ('Push Docker Image') {
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub')
                        dockerapp.push('latest')
                        dockerapp.push("${env.Build_ID}")
                }
            }
        }
    }

}