pipeline {
    agent any
    // ENV definition 
    environment{
        ENV_VAR1 = 'env var-1 value'
        ENV_VAR2 = 'env var-2 value'
        ENV_VAR3 = 'env var-3 value'
    }
    stages {
        stage('parallel'){
            parallel{
                stage('Build') {
                    steps{
                        echo 'Building the webapp ...'
                        echo "The Value of ENV_VAR1 is : ${ENV_VAR1}"
                    }
                }
                stage('Testing') {
                    steps{
                        echo 'Testing '
                        echo "The Value of ENV_VAR2 is : ${ENV_VAR2}"
                    }
                }                          
            }
        }
        stage('Build') {
            steps {
                echo 'Building the webapp ...'
                echo "The Value of ENV_VAR1 is : ${ENV_VAR1}"
                sh 'The Build number is : ${BUILD_NUMBER}| sudo tee -a /root/jenkins/phone.txt > /dev/null' 
                echo 'GIT_BRANCH = ${GIT_BRANCH}'
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
                echo "The Value of ENV_VAR2 is : ${ENV_VAR2}"
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
                echo "The Value of ENV_VAR3 is : ${ENV_VAR3}"
                sh 'echo The Value of ENV_VAR1 is : ${ENV_VAR1} | sudo tee -a /root/jenkins/phone.txt > /dev/null'
                sh 'echo The Value of ENV_VAR2 is : ${ENV_VAR2} | sudo tee -a /root/jenkins/phone.txt > /dev/null'
                sh 'echo The Value of ENV_VAR3 is : ${ENV_VAR3} | sudo tee -a /root/jenkins/phone.txt > /dev/null'
                sh ''' #!/bin/bash -xe 
                ${GIT_BRANCH} | sudo tee -a /root/jenkins/phone.txt
                '''
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
        stage('Priniting the environment variables') {
            when{
                expression{
                    return env.GIT_BRANCH == 'origin/main'
                }
                
            }
            steps {
                echo "Listing all the environment variables"
                sh ''' #!/bin/bash -xe
                printenv | sudo tee -a /root/jenkins/phone.txt
               '''
            }
        }
        

      }
}

