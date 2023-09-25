pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Check Python and pip Versions') {
            steps {
                sh 'python3.10 --version'
                sh 'pip --version'
            }
        }
        stage('Install Project Dependencies') {
            steps {
                sh 'pip install -r requirements.txt'
            }
        }
        stage('Build and Test') {
            steps {
                sh 'docker build -t tuberculosisai:1.0 .'
                sh 'docker run -d -p 5000:5000 tuberculosisai:1.0'
                // Add unit tests here
            }
        }
       
    }
}
