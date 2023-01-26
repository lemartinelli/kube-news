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
    }

}