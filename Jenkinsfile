pipeline {
    agent any
   
    stages {
        stage('test') {
            steps {
                git url: 'https://github.com/11mia/docker-hello-world.git'
	        node.js(nodeJSInstallationName: 'nodejs'){
                		sh 'npm install'
               		sh 'npm run build'
                }
            }
        }
    }
}