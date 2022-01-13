pipeline{
    agent any
    stages{
        stage('SCM checkout'){
            steps{
                git branch: 'main', url: 'https://github.com/vky25/ansible-jenkins-test.git'
            }
        }
         stage('SCM private checkout'){
            steps{
                git branch: 'main', credentialsId: 'git_private_key', url: 'https://github.com/vky25/vault_password_test.git'
            }
         }    
        stage('Execute ansible'){
            steps{
                ansiblePlaybook credentialsId: 'private1-key1', disableHostKeyChecking: true, installation: 'ansible_local', inventory: 'dev.inv', playbook: 'psql_script.yml'
            }
        }

    }
}
