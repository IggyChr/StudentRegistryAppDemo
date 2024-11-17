pipeline {
    agent any

    stages {
        stage ('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/IggyChr/StudentRegistryAppDemo'
            }  
        }

        stage ('install dependencies') {
            steps {
                script {
                    if(isUnix()) {
                        bat 'npm install'
                    } else {
                        bat 'npm install'
                    }
                }
            }
        }

        stage ('starting the applicationa nd run tests') {
            steps {
               script {
                bat 'start /b npm start'
                bat 'npm test'
               } 
            }
        }

        stage ('run tests') {
            steps {
               script {
                bat 'npm test'
               } 
            }
        }
    }

    post {
        always {
            echo "Ci pipeline completed"
        }
    }
}