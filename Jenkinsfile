pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Parineetha-44/PythonCalci.git'
            }
        }
        stage('Verify Python') {
            steps {
                bat 'python --version'
            }
        }
        stage('Install Dependencies') {
            steps {
                bat 'python -m pip install --upgrade pip'
                bat 'pip install -r requirements.txt'
            }
        }
        stage('Run Unit Tests') {
            steps {
                bat 'python -m unittest discover -v'
            }
        }
        stage('Run Application') {
            steps {
                bat 'python calculator.py'
            }
        }
    }
    post {
        success {
            echo 'Build Successful'
        }
        failure {
            echo 'Build Failed'
        }
    }
}
