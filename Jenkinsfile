pipeline {
    agent any

    stages {
        parallel (
        stage('Unit Test') {
            steps {
                script { 
                    sh "cat index.html"
                } 
            }
        }

        stage('Install Dependencies UAT') {
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
                    sshCommand remote: remote, command: 'sudo systemctl stop nginx'
                } 
            }
        }

        stage('Install Dependencies QA') {
            steps {
                script {
                    def remote = [:]
                    remote.name = "${qa_remote_name}"
                    remote.host = "${qa_remote_ip}"
                    remote.user = "${qa_remote_user}"
                    remote.password = "${qa_remote_pass}"
                    remote.allowAnyHosts = true

                    // SSH into the remote server and run the hostname command
                    sshCommand remote: remote, command: 'sudo apt update -y'
                    sshCommand remote: remote, command: 'sudo apt install nginx -y'
                    sshCommand remote: remote, command: 'sudo systemctl stop nginx'
                } 
            }
        }
        )
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
