pipeline {
    agent any

    stages {
        stage('ssh') {
            steps {
                script {
                    def remote = [:]
                    remote.name = '20.14.162.107'
                    remote.host = '20.14.162.107'
                    remote.user = 'student'
                    remote.password = 'Student@123!@#'
                    remote.allowAnyHosts = true

                    // SSH into the remote server and run the hostname command
                    sshCommand remote: remote, command: 'hostname'
                } 
            }
        }
        stage('check_list') {
            steps {
                script {
                    // SSH into the remote server and run the hostname command
                    sshCommand remote: remote, command: 'ls -al'
                } 
            }
        }
    }
}
