pipeline {
    agent any

    stages {
        stage('Restore') {
            steps {
                echo 'Restoring NuGet packages...'
                bat 'dotnet restore'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
                bat 'dotnet build'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                bat 'dotnet test'
            }
        }
    }

    post {
        always {
            echo 'Cleaning up workspace...'
            cleanWs()
        }
    }
}
