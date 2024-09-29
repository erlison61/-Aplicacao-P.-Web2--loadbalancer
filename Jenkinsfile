pipeline {
    agent {
        docker {
            image 'node:20.2.0-alpine3.17'
            args '-p 3000:3000'
        }
    }
    stages {
        stage('Checkout') {
            steps {
                // Faz o checkout do repositório
                checkout scm
            }
        }
        stage('Build') {
            steps {
                // Listar arquivos para depuração
                sh 'ls -la /var/jenkins_home/workspace/project-test'
                
                // Instalar dependências
                sh 'npm install'
                
                // Executar o build
                sh 'CI=false npm run build'
            }
        }
    }
}
