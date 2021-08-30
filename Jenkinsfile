pipeline {
    agent any

    stages {
        stage('git scm update') {
            steps {
                git url: 'https://github.com/11mia/docker-hello-world.git'
            }
        }
            
        stage('build'){
            steps {
                nodejs(nodeJSInstallationName: 'nodejs'){
                sh 'npm install'
                sh 'npm run build'
                }
            }
        }
    }
}