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
        
         stage('export OSSL') {
             steps{
                script{
                    sh "export NODE_OPTIONS=--openssl-legacy-provider"
                }
            }
        }
         stage('INSTALL DEVKIT') {
             steps{
                script{
                    sh "npm install --save-dev @angular-devkit/build-angular"
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
        
        }
        }
