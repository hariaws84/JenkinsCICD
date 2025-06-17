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

         stage('deploying'){
            steps{
                sh ' sudo touch /root/jenkins/pen.txt'
                sh 'echo "hello welcome to jenkins >> /root/jenkins/pen.txt"'
            }
        }
      }
}
