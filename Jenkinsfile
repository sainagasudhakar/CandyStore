pipeline {
    agent any

    stages {
        stage('clone') {
            steps {
                checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Asrith01/CandyStore.git']]) 
            }
        }
        stage('docker') {
            steps {
                script {
                  withDockerRegistry(credentialsId: 'docker-1')  {
                         sh 'docker build -t praveenchinna/candystore .'
                         sh 'docker push praveenchinna/candystore:latest'
                   }
               }
            }
        }
    }
}
