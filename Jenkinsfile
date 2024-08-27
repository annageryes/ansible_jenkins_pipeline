pipeline {
    agent {label 'workers'} // needs to have ssh agent
    parameters{
        choice(name: 'host_type', choices: ['server', 'desktop', 'laptop'], description: 'type of remote host')
        string(name: 'username', defaultValue:'jenkins', description:'user to create, if it does not exists')
        password(name: 'password', defaultValue: 'SECRET', description: 'password for the new user')
        text(name: 'ssh_key', defaultValue: '', description: 'ssh key for future remote connection')
    }
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
                ansiblePlaybook  inventory: 'hosts.txt', playbook: 'main-playbook.yml' ,extraVars: [
            username: "${params.username}",
            password: "${params.password}",
            ssh_key: "${params.ssh_key}"]
            }
        }
        
    }
}