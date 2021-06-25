pipeline {
    agent any
    parameters {
        booleanParam(name: 'Refresh',
                    defaultValue: false,
                    description: 'Read Jenkinsfile and exit.')
		    }
    stages {
        stage('Pre') { 
            steps {
                sh "/home/jenkins/.jenkins/workspace/FlaskApp/ ansible-playbook -vvvv -i inventory.yaml playbook.yaml"
            }
        }
        stage('Test') { 
            steps {
                sh "/home/jenkins/.jenkins/workspace/FlaskApp/ pytest Flask_App/"
            }
        }
        stage('Build & Deploy') {
            steps {
                sh "/home/jenkins/.jenkins/workspace/FlaskApp/ docker-compose up"
            }
        }
    }
}
