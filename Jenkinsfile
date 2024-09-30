pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from GitHub
                git 'https://github.com/sekandarihamid/jenkins-python-app.git'
            }
        }
        
        stage('Install Dependencies') {
            steps {
                // Install Python dependencies from the requirements.txt file
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Run Unit Tests') {
            steps {
                // Run unit tests
                sh 'python -m unittest discover'
            }
        }
    }
    
    post {
        always {
            // Save test results
            junit 'test-results.xml'
        }
    }
}
