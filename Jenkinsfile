pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], userRemoteConfigs: [[url: 'https://github.com/Bharat234/PES2UG21CS234_Jenkins.git']]])
            }
        }

        stage('Build') {
            steps {
                build 'PES2UG21CS234-1'
                sh 'g++ main.cpp -o output'
            }
        }

        stage('Test') {
            steps {
                sh './output'
            }
        }

        stage('Deploy') {
            steps {
                // Add deployment steps here
                echo 'Deploying...'
            }
        }
    }

    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
