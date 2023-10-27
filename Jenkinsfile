pipeline {
    agent any

    stages {
        stage('Init') {
            steps {
                script {
                def remote = [:]
                remote.name = 'localhost'
                remote.host = 'localhost'
                remote.user = 'demouser'
                remote.password = 'Demouser123!@#'
                remote.allowAnyHosts = true
                stage('Remote SSH') {
                sshCommand remote: remote, command: "ls -lrt"
                }
                
                }
            }
        }
    }
}
