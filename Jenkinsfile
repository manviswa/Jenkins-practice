pipeline {
    agent { label 'AGENT-1' }
    stages {
        stage('Build') {
            steps {
                echo "Building...."
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
    }
}

post { 
        always { 
            echo 'I will always say Hello again!'
        }
        success {
            echo "I will run only when the job is success"
        }
        failure {
            echo "I will run only when the job is failure"
        }
    }
}
