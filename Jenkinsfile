pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the webapp ...'
            } 
            post{
                always{
                    echo "This runs always"
                }
                success{
                    echo "This will runs only stage with the success"
                }
                failure{
                    echo "This will run if the stage is failure"
                }
            }
        }
        stage('Testing the webapp'){
            steps{
                echo 'Testing '
            }
            post{
                always{
                    echo "this will runs always"
                }
                success{
                    echo "This will run the stage is success"
                }
                failure{
                    echo "This will run the stage is failure"
                }
            }
        }
        stage ('creating and writing the contents in the file'){
            steps{
                sh ' sudo touch /root/jenkins/phone.txt'
                sh 'echo "hello phone" | sudo tee -a /root/jenkins/phone.txt > /dev/null'
            }
            post{
                always{
                    echo "this will run always"
                }
                success{
                    echo "This will run the stage is success"
                }
                failure {
                    echo "This will run the stage is failure"
                }
            }
        }
      }
}
