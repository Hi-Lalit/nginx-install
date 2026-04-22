pipeline {
    agent any

    stages {
        stage('Checking Ansible version') {
            steps {
                sh 'sudo apt-get update'
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

        stage('Print URL') {
            steps {
                sh '''
                IP=$(curl -s ifconfig.me)
                echo "Access Nginx server at: http://$IP"                
                '''
            }
        }
    }

    post {
        success {
            echo 'Nginx successfully installed and running.'
        }
        failure {
            echo 'Pipeline failed to install and run Nginx.'
        }  
    }
}