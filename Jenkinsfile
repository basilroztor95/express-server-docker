pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Building Docker image...'
                    sh 'sudo docker build . -t express-image'
                }
            }
        }
        stage('Run Container') {
            steps {
                script {
                    echo 'Stopping and removing any previous container...'
                    sh 'sudo docker rm -f express-container'

                    echo 'Starting a new container...'
                    sh 'sudo docker run -d --name express-container -p 3000:3000 express-image'
                }
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
            script {
                echo 'Cleaning up...'
                sh 'sudo docker stop express-container'
                sh 'sudo docker rm express-container'
            }
        }
    }
}
