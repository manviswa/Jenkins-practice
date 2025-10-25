pipeline {
    agent { label 'AGENT-1' }
    options {
        timeout(time: 1, unit: 'HOURS') 
    }
    environment { 
        USER = 'Viswa'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building...."
                sh '''
                  ls -ltr
                  pwd
                  echo "hello world from viswa"
                  printenv
                '''
                //
            }
        }
        stage('Test') {
            steps {
                echo "Testing...."
                //
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploying...."
                //
            }
        }
        stage('example'){
            environment {
                AUTH = credentials('centos')
            }
            steps{
                sh 'printenv'
            }
        }
    }
    post { 
        always { 
            echo "I will always say Hello again!"
        }
        success {
            echo "I will run only when the job is success"
        }
        failure {
            echo "I will run only when the job is failure"
        }
    }
}
