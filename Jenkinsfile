pipeline {
    agent any
    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/firdosneha/devops-prt.git'
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("devops-prt-nginx:latest")
                }
            }
        }
        stage('Run Docker Container') {
            steps {
                script {
                    docker.image("devops-prt-nginx:latest").run("-d -p 80:80")
                }
            }
        }
    }
}
