pipeline {
    agent any

    stages {
        stage('Configure Git') {
            steps {
                sh '''
                  git config user.email "jenkins@ci.local"
                  git config user.name "Jenkins CI"
                '''
            }
        }
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Run Ansible Playbook') {
            steps {
                sh 'ansible-playbook -i inventory.ini playbook.yml'
            }
        }
    }
}
