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
            parallel {
                stage('Install Dependencies UAT') {
                    steps {
                        script {
                            def remoteUAT = [:]
                            remoteUAT.name = "${uat_remote_name}"
                            remoteUAT.host = "${uat_remote_ip}"
                            remoteUAT.user = "${uat_remote_user}"
                            remoteUAT.password = "${uat_remote_pass}"
                            remoteUAT.allowAnyHosts = true

                            sshCommand remote: remoteUAT, command: 'sudo apt update -y'
                            sshCommand remote: remoteUAT, command: 'sudo apt install nginx -y'
                            sshCommand remote: remoteUAT, command: 'sudo systemctl start nginx'
                        }
                    }
                }

                stage('Install Dependencies QA') {
                    steps {
                        script {
                            def remoteQA = [:]
                            remoteQA.name = "${qa_remote_name}"
                            remoteQA.host = "${qa_remote_ip}"
                            remoteQA.user = "${qa_remote_user}"
                            remoteQA.password = "${qa_remote_pass}"
                            remoteQA.allowAnyHosts = true

                            sshCommand remote: remoteQA, command: 'sudo apt update -y'
                            sshCommand remote: remoteQA, command: 'sudo apt install nginx -y'
                            sshCommand remote: remoteQA, command: 'sudo systemctl start nginx'
                        }
                    }
                }
            }
        }
    }
}
