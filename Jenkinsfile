pipeline {
    agent any

    stages {
        stage('install ansible') {
            steps {
                sh 'sudo apt-get update && sudo apt-get install -y python3-pip'
                sh 'sudo pip install ansible'
                sh 'ansible --version'                
            }
        }

        stage('run ansible playbook') {
            steps {
                sh 'sudo ansible-playbook nginx-playbook.yml'
            }
        }  
    }

    post {
        success {
            echo 'Ansible playbook executed successfully.'
        }
        failure {
            echo 'Ansible playbook execution failed.'
        }  
    }

}