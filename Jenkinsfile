pipeline {
    agent any
    
    stages {
        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }
        stage('Run UI Tests') {
            steps {
                bat """
                start /B npm start
                timeout /t 5
                npm test
                """
            }
        } 
    }
}