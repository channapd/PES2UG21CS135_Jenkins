pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                build 'PES2UG21CS135-1'
                sh 'g++ main.cpp -o output'
            }
        }
        stage('Test') {
            steps {
                // Print output of .cpp file using shell script
                sh './output'
            }
        }
        stage('Deploy') {
            steps {
                // Add deployment steps if needed
                echo 'deploy'
            }
        }
    }

    post {
        failure {
            // Display 'pipeline failed' in case of any errors within the pipeline
            echo 'Pipeline failed'
        }
    }
}
