pipeline {
    agent {
        docker {
            image 'maven:3-alpine' 
            args '-p 8000:8000'
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }
}