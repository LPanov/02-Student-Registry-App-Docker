pipeline {
    agent any
    
    stages {
        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }
        stage('Run Tests') {
            failFast true
            parallel {
                stage('Run npm security') {
                    steps {
                        bat 'npm audit'
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
    }
}