pipeline {
    agent {label 'workers'} // needs to have ssh agent
    
    stages {
         stage('pre-requisites'){
            steps{
                echo 'Checking pre-requisites'
            
                sh'''
                    
                    sudo apt-get update
                    sudo apt-get install -y  sshpass 

                '''
            }
        }
        stage('Execute Ansible playbook') {
            steps {
                ansiblePlaybook  inventory: 'hosts.txt', playbook: 'main-playbook.yml'
            }
        }
        
    }
}