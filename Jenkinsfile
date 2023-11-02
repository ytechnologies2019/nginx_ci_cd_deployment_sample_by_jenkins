pipeline {
    agent any

    stages {
        stage('Unit Test') {
            steps {
                script { 
                    sh "cat index.html"
                } 
            }
        }

        stage('Install Dependencies') {
            steps {
                script {
                    def remote = [:]
                    remote.name = "${uat_remote_name}"
                    remote.host = "${uat_remote_ip}"
                    remote.user = "${uat_remote_user}"
                    remote.password = "${uat_remote_pass}"
                    remote.allowAnyHosts = true

                    // SSH into the remote server and run the hostname command
                    sshCommand remote: remote, command: 'sudo apt update -y'
                    sshCommand remote: remote, command: 'sudo apt install nginx -y'
                    sshCommand remote: remote, command: 'sudo systemctl start nginx'
                } 
            }
        }
        //  stage('Install Dependencies') {
        //     steps {
        //         script {
        //             def remote = [:]
        //             remote.name = "${uat_remote_name}"
        //             remote.host = "${uat_remote_ip}"
        //             remote.user = "${uat_remote_user}"
        //             remote.password = "${uat_remote_pass}"
        //             remote.allowAnyHosts = true

        //             // SSH into the remote server and run the hostname command
        //             sshCommand remote: remote, command: 'sudo apt update -y'
        //             sshCommand remote: remote, command: 'sudo apt install nginx -y'
        //             sshCommand remote: remote, command: 'sudo systemctl start nginx'
        //         } 
        //     }
        // }
    }
}
