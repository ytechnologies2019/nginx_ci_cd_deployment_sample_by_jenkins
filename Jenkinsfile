pipeline {
    agent any

    stages {
        stage('Init') {
            steps {
                script {
                    def remote = [
                        name: '20.14.162.107',
                        host: '20.14.162.107',
                        user: 'student',
                        password: 'Student@123!@#',
                        allowAnyHosts: true
                    ]
                    stage('Remote SSH') {
                        sshagent(credentials: ['<SSH_CREDENTIALS_ID>']) {
                            sh "sshpass -p ${remote.password} ssh ${remote.user}@${remote.host} 'ls -lrt'"
                        }
                    }
                }
            }
        }
    }
}
