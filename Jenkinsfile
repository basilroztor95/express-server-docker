pipeline {
        agent any
        stages {
                stage('Build') {
                        steps {
                                echo 'Building...'
                                sh 'sudo docker build . -t express-image'
                                sh 'sudo docker create --name express-container -p 3000:3000 express-image'
                                sh 'sudo docker start express-container'
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
                        }
                }
        }
}
