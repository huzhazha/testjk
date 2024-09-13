pipeline {
    agent any
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                sh '''
                 cd myapp
                 python3 python.py
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                 echo "Testing.sh."
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver....'
                sh '''
                echo "doing delivery stuff.."
                '''
            }
        }
    }
}