pipeline{
    agent any
    stages{
        stage('SCM checkout'){
            steps{
                git branch: 'main', url: 'https://github.com/vky25/ansible-jenkins-test.git'
            }
        }
        stage('Execute ansible'){
            steps{
                ansiblePlaybook credentialsId: 'private1-key1', disableHostKeyChecking: true, installation: 'ansible_local', inventory: 'dev.inv', playbook: 'psql_script.yml'
            }
        }

    }
}
