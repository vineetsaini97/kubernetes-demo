pipeline {
    agent any
    
    environment {
        KUBECONFIG = 'C:\\Users\\Dinesh\\.kube\\config'
    }

    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/vineetsaini97/kubernetes-demo.git'
            }
        }

        stage('Deploy MySQL') {
            steps {
                bat 'kubectl apply -f mysql-deployment.yaml'
                bat 'kubectl apply -f mysql-service.yaml'
            }
        }

        stage('Deploy phpMyAdmin') {
            steps {
                bat 'kubectl apply -f phpmyadmin-deployment.yaml'
                bat 'kubectl apply -f phpmyadmin-service.yaml'
            }
        }

        stage('Deploy Backend') {
            steps {
                bat 'kubectl apply -f backend-deployment.yaml'
                bat 'kubectl apply -f backend-service.yaml'
            }
        }

        stage('Deploy Frontend') {
            steps {
                bat 'kubectl apply -f frontend-deployment.yaml'
                bat 'kubectl apply -f frontend-service.yaml'
            }
        }
    }
}
