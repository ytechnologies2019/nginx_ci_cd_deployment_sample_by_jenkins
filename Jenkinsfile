pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
                script {
                    def remote = [:]
                    remote.name = '20.14.162.107'
                    remote.host = '20.14.162.107'
                    remote.user = 'student'
                    remote.password = 'Student@123!@#'
                    remote.allowAnyHosts = true

                    // SSH into the remote server and run the hostname command
                    sshCommand remote: remote, command: 'sudo apt update -y'
                    sshCommand remote: remote, command: 'sudo apt install nginx -y'
                } 
            }
        }
        stage('check_list') {
            steps {
                script {
                    def remote = [:]
                    remote.name = '20.14.162.107'
                    remote.host = '20.14.162.107'
                    remote.user = 'student'
                    remote.password = 'Student@123!@#'
                    remote.allowAnyHosts = true

                    // SSH into the remote server and run the hostname command
                    sshCommand remote: remote, command: 'ls -al'
                } 
            }
        }
    }
}
