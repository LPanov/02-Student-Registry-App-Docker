pipeline {
    agent any
    
    stages {
        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }
        stage('Build Application') {
            steps {
                bat 'npm start &'
            }
        }
        stage('Run UI Tests') {
            steps {
                bat 'npm test'
            }
        } 
    }
}