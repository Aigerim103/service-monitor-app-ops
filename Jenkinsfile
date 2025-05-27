pipeline {
    agent any
    environment {
        DOCKER_IMAGE = 'service-monitor-app'
    }
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/Aigerim103/service-monitor-app.git', branch: 'main'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    docker.build(env.DOCKER_IMAGE)
                }
            }
        }
        stage('Run Docker Container') {
           steps {
                bat 'docker-compose up -d --build'
            }
        }
    }
}
