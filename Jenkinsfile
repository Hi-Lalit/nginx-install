pipeline {
    agent any

    stages {
        stage('Install Ansible') {
            steps {
                sh '''
               
                sudo apt-get update
                sudo apt-get install -y ansible        
                '''
                sh 'ansible --version'      
            }
        }

        stage('Run Ansible Playbook') {
            steps {
                ansiblePlaybook(
                    playbook: 'nginx-playbook.yml',                    
                    credentialsId: 'aws-ec2-ssh',
                    disableHostKeyChecking: true
                )
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