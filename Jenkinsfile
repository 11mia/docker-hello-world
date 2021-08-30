pipeline {
    agent any

    environment {
        SLACK_CHANNEL = '#jenkins'
    }

    stages {
        stage('Start') {
                steps {
                    slackSend (channel: SLACK_CHANNEL, color: '#FFFF00', message: "STARTED: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")
                }
        }

        stage('git scm update') {
            steps {
                git url: 'https://github.com/11mia/docker-hello-world.git'
            }
        }
            
        stage('build'){
            steps {
                nodejs(nodeJSInstallationName: 'nodejs'){
                sh 'npm install'
                sh 'npm run'
                }
            }
        }
    }

    post {
        success {
            slackSend (channel: SLACK_CHANNEL, color: '#00FF00', message: "SUCCESSFUL: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")
        }
        failure {
            slackSend (channel: SLACK_CHANNEL, color: '#FF0000', message: "FAILED: Job '${env.JOB_NAME} [${env.BUILD_NUMBER}]' (${env.BUILD_URL})")
        }
    }
}