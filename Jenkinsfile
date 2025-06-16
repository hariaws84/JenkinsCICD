pipeline {
    agent any

    stages {
        stage('build') {
          steps {
            sh 'echo "Building" '
            
          }
        stage('Creating the file'){
          steps{
            sh 'touch /var/lib/jenkins/hariharan1.txt'
            sh 'echo "Hello hariharan " >> /var/lib/jenkins/hariharan1.txt'
            
          }
        }
