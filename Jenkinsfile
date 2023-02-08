pipeline {
    agent any
    stages {
        stage('Checkout Code') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/CeeyIT-Solutions/flask-app.git']]])
            }
        }
        stage('Deploy') {
            steps {
                sh '''
                ansible-playbook flask.yaml -i hosts.ini
                '''
            }
        }
    }
}
