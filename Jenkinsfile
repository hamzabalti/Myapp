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
        }
        }
