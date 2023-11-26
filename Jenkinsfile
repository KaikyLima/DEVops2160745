pipeline {
    agent any
    
    stages {
        stage('Declarative: Checkout SCM') {
            steps {
                checkout scm
            }
        }

        stage('Instalacao npm') {
            steps {
                echo 'Instalando...'
                sh 'npm ci'
            }   
        }

    }
}
