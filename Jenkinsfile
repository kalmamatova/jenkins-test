pipeline {
    agent any
    //environment {
        //GITHUB_TOKEN = credentials('github-creds')
    //}
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    echo 'pip install -r requirements.txt'
//                    sh 'pip3 install -r requirements.txt'
                }
            }
        }

        stage('Run Tests') {
            steps {
                script {
                    echo 'python -m unittest discover' 
 //                   sh 'python -m unittest discover'
                }
            }
        }
        stage('Deploy') {
            when {
                expression {
                    BRANCH_NAME == 'main' || BRANCH_NAME == 'prod'
                }
            }
            steps {
                echo 'deploying...'
            }
        }
    }
}

