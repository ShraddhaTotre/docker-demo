pipeline {

    agent any

    stages {

        stage('Clone') {
            steps {
                echo 'Repository cloned'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t docker-demo:v1 .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker rm -f docker-demo-container || true
                docker run -d --name docker-demo-container -p 8081:80 docker-demo:v1
                '''
            }
        }

    }
}
