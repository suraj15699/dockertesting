pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    dockerImage = docker.build("hello-python-image")
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    dockerImage.inside {
                        sh 'python --version'
                        sh 'python hello.py'
                    }
                }
            }
        }
    }
}
