pipeline {
    agent any 
    stages {
        stage('Pre') { 
            steps {
                sh "/home/jenkins/.local/bin/ansible-playbook -i ansible/inventory ansible/playbook.yaml"
            }
        }
        stage('Test') { 
            steps {
                sh "/home/jenkins/.local/bin/pytest Flask_App/"
            }
        }
        stage('Build & Deploy') {
            steps {
                sh "/home/jenkins/.local/bin/docker-compose up"
            }
        }
    }
}
