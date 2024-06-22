pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("my-webapp:latest", ".")
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    def customImage = docker.image("my-webapp:latest")
                    customImage.run("-p 8083:80")
                }
            }
        }
    }
}
