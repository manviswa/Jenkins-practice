pipeline {
    agent { label 'AGENT-1' }
    options {
        timeout(time: 1, unit: 'HOURS') 
    }
    environment { 
        USER = 'Viswa'
    }
    triggers {
        cron('* * * * *')
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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
        stage('Params') {
            steps {
                echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
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
