pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                    branches: [[name: '/main']],
                    userRemoteConfigs: [[url: 'https://github.com/CASHIKPOOJARY/PES1UG22CS150_Jenkins.git']]
                ])
            }
        }

        stage('Build') {
            steps {
                build 'PES2UG19CS5150-1'
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
                echo 'deploy'
            }
        }
    }

    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
