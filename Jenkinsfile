pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                script {
                    git branch: 'test', credentialsID: 'jenkins_test', url: 'https://github.com/kalmamatova/jenkins-test.git'
                }
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    sh 'sudo apt install python3-pip && pip install -r requirements.txt'
                }
            }
        }

        stage('Run Tests') {
            steps {
                script {
                    sh 'python -m unittest discover'
                }
            }
         }
    }
}
