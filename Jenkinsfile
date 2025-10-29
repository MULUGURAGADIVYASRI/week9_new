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
                bat 'docker tag registration:v1 ragadivyasri/registration:v1'
                bat 'docker push ragadivyasri/registration:v1'
            }
        }
        stage('Deploy to Kubernetes') {
            steps {
                bat 'kubectl apply -f C:/Users/Krish/OneDrive/Desktop/Raagaa/Week-2/deployment.yaml'
                bat 'kubectl apply -f C:/Users/Krish/OneDrive/Desktop/Raagaa/Week-2/service.yaml'
            }
        }
        stage(&#39;Automated UI Test&#39;) {
steps {
bat 'python C:/Users/Krish/OneDrive/Desktop/Raagaa/Week-2/tests/test_registration.py';
}
}
    }
}
