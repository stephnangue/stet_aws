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
                    remoteTrigger('http://172.16.32.65:8080/', 'SABr%20CD/main') {
                        parameter('VERSION', '$PIPELINE_VERSION')
                        parameters(BRANCH: 'feature-A', STAGING_REPO_ID: '41234232')
                        blockBuildUntilComplete()
                    }
                } 
            }          
        }
    }
}
