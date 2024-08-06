pipeline {
    agent any
    
    stages {
       
        stage('Execute Ansible playbook') {
            steps {
                ansiblePlaybook playbook: 'main-playbook.yml -i hosts.txt'
            }
        }
        
    }
}