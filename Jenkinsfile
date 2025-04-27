pipeline {
    agent any
    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/venkatesh669/simple-devops.git'
            }
        }
    
        stage('Docker Build & Push') {
            steps {
                sh 'docker build -t venkatesh86/simple-devops .'
                sh 'docker push venkatesh86/yourdockerhub:tagname'
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

