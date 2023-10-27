pipeline { 
    agent any 
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Build') { 
            steps { 
                sh 'ls -alht' 
            }
        }
        stage('Test'){
            steps {
                sh 'whoami'
            }
        }
        stage('Deploy') {
            steps {
                sh 'hostname'
            }
        }
    }
}