pipeline {
    agent any

    stages {
        stage('Init') {
            steps {
                 def remote = [:]
                remote.name = 'test'
                remote.host = 'test.domain.com'
                remote.user = 'root'
                remote.password = 'password'
                remote.allowAnyHosts = true
                stage('Remote SSH') {
                sshCommand remote: remote, command: "ls -lrt"
                }
            }
        }
    }
}
