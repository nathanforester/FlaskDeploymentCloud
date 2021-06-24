pipeline {
    agent any 
    stages {
        stage('Pre') { 
            steps {
                sh "cd /home/jenkins/.local/bin/ && ansible-playbook -v -i --inventory.yaml --playbook.yaml"
            }
        }
        stage('Test') { 
            steps {
                sh "cd /home/jenkins/.local/bin/ && pytest Flask_App/"
            }
        }
        stage('Build & Deploy') {
            steps {
                sh "cd /home/jenkins/.local/bin/ && docker-compose up"
            }
        }
    }
}
