 pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Lion-Technology-Solutions/ansible-jenkins-projects.git'
            }
        }
        stage('Deploy with Ansible') {
            steps {
                ansiblePlaybook(
                    playbook: '02-deploy-users.yaml',
                    inventory: 'inventory.ini',
                    credentialsId: 'ansible-ssh-key',
                    extras: '--verbose'
                )
            }
        }
    }
}