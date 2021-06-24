pipeline {
    agent any 
    stages {
        stage('Pre') { 
            steps {
                sh "ansible-playbook -v -i inventory.yaml playbook.yaml"
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
