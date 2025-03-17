pipeline{
    agent any
    stages{
        stage('Clone Repository from GitHub'){
            steps{
                echo "========clone start========"
                git branch: 'main', url: 'https://github.com/andrii-br/Repo-jenkinsfile.git'
            }
        }    
        stage('Build Docker image'){
            steps{
                echo "========start build========"
                sh 'dcoker compose build -t . app-jenkins:1.0'
            }
        }
        stage('Run docker conteiner'){
            steps{
                echo "========start Run docker conteiner========"
                sh 'docker compose up -d'
            }
        }  
        stage('Test appp'){
            steps{
                sh 'sleep 5'
                sh 'curl -i http://localhost:8000'
            }
        }
        stage('Stop app'){
            steps{
                sh 'docker compose down'
            }
        }
        
        
    }
}