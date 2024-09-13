pipeline {
    agent {
        node{
            label 'docker-agent-python'
        }
    }
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                sh '''
                 cd myapp
                 sudo apt install python3.11-venv
                 python3 -m venv .venv
                 source .venv/bin/activate
                
                 pip install -r requirements.txt
                 
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                 cd myapp
                 python3 python.py
                 python3 python.py --name=dddd
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