pipeline { 
    agent any 
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Build') { 
            steps { 
                sh 'ls ' 
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