pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/kaweeo/SEDO-Exam-prep-2-1.git'
            }
        }
        stage('Setup .NET') {
            steps {
                sh 'curl -sSL https://dot.net/v1/dotnet-install.sh | bash -s -- --version 6.0.100'
                sh 'export PATH=$HOME/.dotnet:$PATH'
            }
        }
        stage('Restore') {
            steps {
                sh 'dotnet restore'
            }
        }
        stage('Build') {
            steps {
                sh 'dotnet build --no-restore'
            }
        }
        stage('Test') {
            steps {
                sh 'dotnet test'
            }
        }
    }
}