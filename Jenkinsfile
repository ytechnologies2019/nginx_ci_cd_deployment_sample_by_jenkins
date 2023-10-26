pipeline {
    agent any
    stages {
        stage('Hello') {
            steps {
                script {
                def remote = [:]
                remote.name = '172.172.13.50'
                remote.host = '172.172.13.50'
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
