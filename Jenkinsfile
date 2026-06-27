pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out source code...'
                git 'https://github.com/Manjunath-Kapanaiah/JAVA_CI_DEMO.git'
                checkout scm
            }
        }
        
        stage('Build') {
            steps {
                echo 'Building the project...'
                sh 'mvn clean compile'
            }
        }
        
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'mvn test'
            }
        }
        
        stage('Package') {
            steps {
                echo 'Packaging the application...'
                sh 'mvn package'
            }
        }
    }
    
    post {
        always {
            echo 'Pipeline execution completed.'
        }
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
