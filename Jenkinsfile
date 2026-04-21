pipeline {
    agent any

    stages {
        stage('install ansible') {
            steps {
                sh 'apt-get update && apt-get install -y python3-pip'
                sh 'pip install ansible'
                sh 'ansible --version'                
            }
        }

        stage('run ansible playbook') {
            steps {
                sh 'ansible-playbook -i inventory.ini nginx-playbook.yml'
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