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
        
        stage('Install NPM') {
             steps{
                script{
                    sh "npm install"
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
        
         stage('Build') {
             steps{
                script{
                    sh "export NODE_OPTIONS=--openssl-legacy-provider"
                    sh " ansible-playbook Ansible/build.yml -i Ansible/inventory/host.yml"
                }
            }
        }
        
        }
        }
