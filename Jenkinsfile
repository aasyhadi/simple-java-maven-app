pipeline {
    agent {
        docker {
            image 'node:lts-bullseye-slim'
            args '-p 8000:8000'
        }
    }
    stages {
        stage('Build') {
            steps {
                input message: 'Proceed to the Deploy stage?'
                    echo "Deploying App"
                    sh "cd jenkins/scripts && ls"
                    sh "./jenkins/scripts/dockerize.sh"
                    echo "120 seconds for test before the app shutdown"
                    sleep 120 // seconds
                    echo "Shutting Down Apps"
            }
        }
    }
    stage('Test') {
        steps {
            sh './jenkins/scripts/test.sh'
        }
    }
}