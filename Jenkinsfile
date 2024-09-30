pipeline {
    agent any

    stages {
        stage('Clone repository') {
            steps {
                git 'https://github.com/sekandarihamid/jenkins-python-app.git'
            }
        }

        stage('Install dependencies') {
            steps {
                sh 'python3 -m venv venv'
                sh './venv/bin/pip install -r requirements.txt'
            }
        }

        stage('Run tests') {
            steps {
                sh './venv/bin/python -m unittest discover -s .'
            }
        }
    }

    post {
        always {
            junit 'test-results.xml'
        }
    }
}
