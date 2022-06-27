pipeline {
  agent none

    stages {
        stage('Checkout') {
            checkout scm
        }
        stage('Quality Test') {
            echo "Running Quality tests"
        }
        stage('Unit Test') {
            echo "Running Unit tests"
        }
        stage('Security Test') {
            echo "Running Security tests"
        }
        stage('Build') {
            echo "Building artifact"
        }
        stage('Push') {
            echo "Storing artifact"
        }
        stage('Tigger CD') {
            echo "Tiggering CD Pipeline"
        }
    }
}
