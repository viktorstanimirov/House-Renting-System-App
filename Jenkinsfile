pipeline {
    agent any

    environment {
        DOTNET_VERSION = '6.0.x'
    }

    stages {
        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }

        stage('Setup .NET Core') {
            steps {
                script {
                    bat 'dotnet --version'
                }
            }
        }

        stage('Restore Dependencies') {
            steps {
                script {
                    bat 'dotnet restore'
                }
            }
        }

        stage('Build App') {
            steps {
                script {
                    bat 'dotnet build --no-restore'
                }
            }
        }

        stage('Run Tests') {
            steps {
                script {
                    bat 'dotnet test --no-build --verbosity normal'
                }
            }
        }
    }
}
