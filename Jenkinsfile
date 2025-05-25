pipeline {
    agent any

    environment {
        VENV = 'venv'
    }

    stages {
        stage('Checkout') {
            steps {
                git credentialsId: 'github-token', url: 'https://github.com/Nixk01/Pytst.git'
            }
        }
        stage('Setup Python Environment') {
            steps {
                sh '''
                    python3 -m venv $VENV
                    source $VENV/bin/activate
                    pip install --upgrade pip
                    pip install -r requirements.txt
                '''
            }
        }
        stage('Run Tests') {
            steps {
                sh '''
                    source $VENV/bin/activate
                    pytest --junitxml=results.xml
                '''
            }
        }
    }

    post {
        always {
            junit 'results.xml'
        }
    }
}
