pipeline {
  agent any
    stages {
        stage('Pull') {
             steps{
                script{
                    checkout([$class: 'GitSCM', branches: [[name: '*/main']],
                        userRemoteConfigs: [[
                            credentialsId: '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',
                            url: 'https://github.com/hamzabalti/Myapp.git']]])
                }
            }
        }
        
         stage('Build') {
             steps{
                script{
                    sh "sudo ansible-playbook Ansible/build.yml -i Ansible/inventory/host.yml"
                }
            }
        }
        
        }
        }
