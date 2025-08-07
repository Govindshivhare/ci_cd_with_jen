pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/Govindshivhare/ci_cd_with_jen.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t ci_cd_with_jen .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker rm -f my-running-web || true'
                sh 'docker run -d -p 8080:80 --name my-running-web ci_cd_with_jen'
            }
        }
    }
}