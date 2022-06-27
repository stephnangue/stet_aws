pipeline {
  agent any

    stages {
        stage('Checkout') {
            steps{
                checkout scm
            }
        }
        stage('Quality Test') {
            steps{
                echo "Running Quality tests"
            }
        }
        stage('Unit Test') {
            steps{
                echo "Running Unit tests"
            }
        }
        stage('Security Test') {
            steps{
                echo "Running Security tests"
            }          
        }
        stage('Build') {
            steps{
                echo "Building artifact"
            }          
        }
        stage('Push') {
            steps{
                echo "Storing artifact"
            }          
        }
        stage('Tigger CD') {
            steps{
                script{
                    def handle = triggerRemoteJob job: 'SABr%20CD/main', remoteJenkinsName: 'remoteJenkins'
                  
                } 
            }          
        }
    }
}
