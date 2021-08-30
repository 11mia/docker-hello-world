pipeline {
    agent any
    tools {node.js "nodejs"}

    stages {
        stage('test') {
            steps {
                git url: 'https://github.com/11mia/docker-hello-world.git'
                sh 'npm install'
                sh 'npm run build'
            }
        }
    }
}