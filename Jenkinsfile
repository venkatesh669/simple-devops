pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/venkatesh669/simple-devops.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn -f app/pom.xml clean package'
            }
        }
        stage('Docker Build & Push') {
            steps {
                sh 'docker build -t yourdockerhub/simple-app .'
                sh 'docker push yourdockerhub/simple-app'
            }
        }
        stage('Terraform Apply') {
            steps {
                dir('terraform') {
                    sh 'terraform init'
                    sh 'terraform apply -auto-approve'
                }
            }
        }
    }
}

