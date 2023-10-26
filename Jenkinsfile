pipeline {
    agent any
    stages {
        stage('Hello') {
            steps {
                script {
                def remote = [:]
                remote.name = '172.200.2.244'
                remote.host = '172.200.2.244'
                remote.user = 'demouser'
                remote.password = 'Demouser123!@#'
                remote.allowAnyHosts = true
                stage('Remote SSH') {
                }
            }
        }
    }
  }
}
