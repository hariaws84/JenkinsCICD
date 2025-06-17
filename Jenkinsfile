pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the webapp ...'
            }   //EOL Stage test 
        }
        stage('Testing the webapp'){
            steps{
                echo 'Testing '
            }
        }
        stage ('creating and writing the contents in the file'){
            steps{
                sh ' sudo touch /root/jenkins/phone.txt'
                sh 'echo "hello phone" | sudo tee -a /root/jenkins/phone.txt > /dev/null'
            }
        }
      }
}
