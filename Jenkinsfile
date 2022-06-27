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
                    //WARNING -> this is note secure : tokens should not be used as pain text in the source code
                    sh "curl -X POST http://stephane:1142522db6c8940099b7c23a269d451036@172.16.32.65:8080/job/SABr%20CD/job/" + env.BRANCH_NAME + "/buildWithParameters?param1=162&param2=store"
                } 
            }          
        }
    }
}
