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
                if(isUnix()) {
                    bat 'npm install'
                } else {
                    bat 'npm install'
                }
            }
        }

        stage ('starting the applicationa nd run tests') {
            steps {
               script {
                bat 'npm start &'
                bat 'wait-on http://localhost:8090'
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