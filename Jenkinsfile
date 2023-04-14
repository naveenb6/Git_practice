pipeline {
    agent any
    stages {
        stage('Checkout Git repository') {
            steps {
                git branch: 'main', url: ' https://github.com/naveenb6/Git_practice.git'
            }
        }
        stage('Build Docker image') {
            steps {
                script {
                    def dockerfile = 'dockerfile'
                    def registry = 'localhost:5000'
                    def imageName = 'myimage'
                    def imageTag = 'latest'
                    def dockerImage = docker.build("${registry}/${imageName}:${imageTag}", "-f ${dockerfile} .")
                    dockerImage.push()
                }
            }
        }
    }
}
