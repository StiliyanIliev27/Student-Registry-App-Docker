pipeline {
    agent any
    stages {
        stage('Install Dependencies') {
            steps {
                echo 'Installing dependencies...'
                bat 'npm install'
            }
        }
        stage("Parallel Execution"){
            parallel{
                stage('Run npm audit tests') {
                    steps {
                        echo 'Starting the application...'
                        bat 'npm audit'
                        }
                    }
                stage('Run Tests') {
                    steps {
                        echo 'Running tests...'
                        bat 'npm test'
                    }
                }
            }
        }
    }
}
