pipeline {
    agent any 
    stages {
        stage('Pre') { 
            steps {
                sh "cd /home/jenkins/.jenkins/workspace/FlaskApp ansible-playbook -vvvv -i inventory.yaml playbook.yaml"
            }
        }
        stage('Test') { 
            steps {
                sh "pytest Flask_App/"
            }
        }
        stage('Build & Deploy') {
            steps {
                sh "docker-compose up"
            }
        }
    }
}
