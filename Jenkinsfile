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
 
      

         /*   stage('install') {
             steps{
                script{
                    sh " npm install --save-dev @angular-devkit/build-angular"
                }
            }
        }
         stage('Build') {
             steps{
                script{
                    sh " ansible-playbook Ansible/build.yml -i Ansible/inventory/host.yml"
                }
            }
        }
        
        stage('docker') {
             steps{
                script{
                    sh "ansible-playbook Ansible/docker.yml -i Ansible/inventory/host.yml "
                }
            }
        }
        */
            
        stage('push docker hub') {
             steps{
                script{
                    sh "ansible-playbook Ansible/docker-registry.yml -i Ansible/inventory/host.yml "
                }
            }
        }
        
        
        }
        }
