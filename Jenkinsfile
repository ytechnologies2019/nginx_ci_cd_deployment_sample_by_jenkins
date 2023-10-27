pipeline {
    agent any

    stages {
        stage('Init') {
            steps {
                script {
                    def remote = [:]
                    remote.name = '20.14.162.107'
                    remote.host = '20.14.162.107'
                    remote.user = 'student'
                    remote.password = 'Student@123!@#'
                    remote.allowAnyHosts = true

                    // SSH into the remote server and run the hostname command
                    def result = sshCommand remote: remote, command: 'hostname', returnStatus: true

                    // Check the result of the command
                    if (result == 0) {
                        echo "Remote hostname: ${stdout.trim()}"
                    } else {
                        error "Failed to retrieve remote hostname"
                    }
                }
            }
        }
    }
}
