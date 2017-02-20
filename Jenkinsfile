pipeline {
    agent any
    parameters {
        string(name: 'miVariable', defaultValue: 'Hello', description: 'Escribe algo')
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building ${miVariable}..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
