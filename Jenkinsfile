pipeline {
    agent any
    tools{
        ansible "Ansible"
    }

    stages {
        stage('git checkout') {
            steps {
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'RishabhKishnatray', url: 'https://github.com/RishabhKishnatray/elasticsearch.git']])
            }
        }
    stage('ansible') {
            steps {
               ansiblePlaybook credentialsId: 'ubuntu', disableHostKeyChecking: true, installation: 'Ansible', inventory: 'aws_ec2.yml', playbook: 'playbook.yml'
            }
        }
    
        
        
    }
}
