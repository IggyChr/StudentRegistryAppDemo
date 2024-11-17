pipeline {
    agent any

    environment {
        NODE_VERSIONS = '20.x'
    }

    tools {
        nodejs "${NODE_VERSIONS}"
    }

    stages {
        stage ('Checkout') {
            steps {
                checkout scm
            }  
        }

        stage ('install dependencies') {
            steps {
                if(isUnix()) {
                    sh 'npm install'
                } else {
                    sh 'npm install'
                }
            }
        }

        stage ('starting the applicationa nd run tests') {
            steps {
               script {
                sh 'npm start &'
                sh 'wait-on http://localhost:8090'
                sh 'npm test'
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