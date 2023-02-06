pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/CeeyIT-Solutions/flask-app.git']]])
            }
        }
        stage('Deploy') {
            steps {
                script {
                    ansiblePlaybook(
                        playbook: 'flask.yml',
                        extraVars: [
                            g1: 'g1'
                        ],
                        inventory: 'hosts.ini'
                    )
                }
            }
        }
    }
}
