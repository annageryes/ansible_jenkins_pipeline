pipeline {
    agent any
    
    stages {
       
        stage('Execute Ansible playbook') {
            steps {
                ansiblePlaybook  inventory: 'hosts.txt', playbook: 'main-playbook.yml'
            }
        }
        
    }
}