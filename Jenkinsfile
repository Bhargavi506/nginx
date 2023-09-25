pipeline {
    agent any
    
    stages {
        stage('Build') {
           steps {
                script {
                    sh 'docker build -t my-nginx-app .'
                }
            }
        }
        
        stage('Deploy to Kubernetes') {
            steps {
                script {
                    sh 'kubectl apply -f nginx-deployment.yaml'
                }
            }
        }
        
        stage('Expose Service') {
            steps {
                script {
                    sh 'kubectl apply -f service-nginx.yaml'
                }
            }
        }
    }
}
