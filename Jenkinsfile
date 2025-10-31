pipeline {
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t registration:v1 .'
            }
        }
        stage('Push to Docker Hub') {
            steps {
                bat 'docker tag registration:v1 shravani152004/registration:v1'
                bat 'docker push shravani152004/registration:v1'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f C:/Users/Admin/Desktop/week9_new-main/deployment.yaml'
                bat 'kubectl apply -f C:/Users/Admin/Desktop/week9_new-main/service.yaml'
            }
        }
        stage('Automated UI Test') {
steps {
bat 'python  C:/Users/Admin/Desktop/week9_new-main/tests/test_registration_app.py';
}
}
    }
}
