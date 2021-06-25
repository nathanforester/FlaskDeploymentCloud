pipeline {
    agent any 
    stages {
        stage('Pre') { 
            steps {
                sh "
		cd /home/jenkins/.jenkins/workspace/FlaskApp/ && ansible-playbook -vvvv -i inventory.yaml playbook.yaml
		"
            }
        }
        stage('Test') { 
            steps {
                sh "
		cd /home/jenkins/.jenkins/workspace/FlaskApp/ && pytest Flask_App/
		"
            }
        }
        stage('Build & Deploy') {
            steps {
                sh "
		cd /home/jenkins/.jenkins/workspace/FlaskApp/ && docker-compose up
		"
            }
        }
    }
}
