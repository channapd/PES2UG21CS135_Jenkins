pipeline {
    agent any

    stages {
        stage('Clone repository') {
          steps{
            checkout([$class: 'GitSCM',
            branches: [[name: '*/main']],
            userRemoteConfigs: [[url: 'https://github.com/channapd/PES2UG21CS135_Jenkins.git']]])
          }
        }
        stage('Build') {
            steps {
                build 'PES2UG21CS135'
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
