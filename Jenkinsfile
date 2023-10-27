pipeline {
    agent any

    stages {
        stage('SSH_LOGIN') {
            steps {
                script {
                    def remote = [:]
                    remote.name = '20.14.162.107'
                    remote.host = '20.14.162.107'
                    remote.user = 'student'
                    remote.password = 'Student@123!@#'
                    remote.allowAnyHosts = true
                }
            }
        }
        stage('Remote SSH') {
            steps {
                sshCommand remote: remote, command: "ls -lrt"
            }
        }
    }
}
