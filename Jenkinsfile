pipeline {
  agent any

    stages {
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
                    withCredentials([string(credentialsId: 'remote_jenkins_token', variable: 'TOKEN')]) {
                        //WARNING -> Don't forget to allow the use of a static method in a jenkins script (Administrer Jenkins -> In-process Script Approval)
                        def token = hudson.util.Secret.fromString("$TOKEN")
                      
                        def handle = triggerRemoteJob(
                            job: 'http://172.16.32.65:8080/job/SABr%20CD/job/'+ env.BRANCH_NAME,
                            auth: TokenAuth(apiToken: token, userName: 'stephane'),
                            parameters: 'SABR_MOTEUR_VERSION=1.2.14\nSABR_IHM_VERSION=2.5.34\nSIMULATEUR_VERSION=12.4.23')
                    }
                } 
            }          
        }
    }
}
