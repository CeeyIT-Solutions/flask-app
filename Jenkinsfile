pipeline {
  agent any
  stages {
    stage('Ansible Deployment') {
      steps {
        script {
          ansiblePlaybook(
            playbook: 'flask.yaml',
            inventory: 'hosts.ini'
          )
        }
      }
    }
  }
}

