pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                    echo 'Building Docker image...'
                    sh 'docker build . -t express-image'
            }
        }
        stage('Run Container') {
            steps {
                    echo 'Stopping and removing any previous container...'
                    sh 'docker rm -f express-container'

                    echo 'Starting a new container...'
                    sh 'docker run -d --name express-container -p 3000:3000 express-image'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // Add deployment steps here
            }
        }
    }
    post {
        always {
                echo 'Cleaning up...'
                sh 'docker stop express-container'
                sh 'docker rm express-container'
        }
    }
}
