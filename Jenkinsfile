pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/YOUR_USERNAME/my-static-web.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t my-static-web .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh 'docker rm -f my-running-web || true'
                sh 'docker run -d -p 8080:80 --name my-running-web my-static-web'
            }
        }
    }
}
