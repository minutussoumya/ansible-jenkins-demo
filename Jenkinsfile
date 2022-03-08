pipeline {
    agent any
     
    stages {
      stage('checkout') {
           steps {
             
                git branch: 'main', url: 'https://github.com/Neelam-zanvar/ansible-neelam.git'
             
          }
        }
        
        
        
          stage('Ansible Init') {
            steps {
                script {
                
               def tfHome = tool name: 'ansible2'
                env.PATH = "${tfHome}:${env.PATH}"
                 sh 'ansible --version'
                    
            }
            }
        }
        
        
        
        stage('Ansible Deploy') {
             
            steps {
                 
             
               
               sh "ansible-playbook main.yml -i inventories/dev/hosts --user jenkins --key-file ~/.ssh/id_rsa -e '@configs/dev.yml'"

               
            
            }
        }
    }
}
