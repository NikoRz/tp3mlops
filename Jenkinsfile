pipeline {
    agent any

    environment {
        PATH = "C:\\Windows\\System32;
        C:\\Users\\nicop\\AppData\\Local\\Programs\\Python\\Python39;
        C:\\Program Files\\Docker\\Docker\\resources\\bin"
    }

    stages {
        stage('Building') {
            steps {
                git branch: 'main', url: 'https://github.com/NikoRz/tp3mlops.git'
            }
        }
        stage('Testing') {
            steps {
                bat 'python -m pip install Flask'
                bat 'python test_main.py'
            }
        }
        stage('Deploying') {
            steps {
                bat 'docker build -t jenkins_app .'
                bat 'docker run -d jenkins_app'
            }
        }
    }
}
