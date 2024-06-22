pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Aucune action de checkout nécessaire ici
            }
        }

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
