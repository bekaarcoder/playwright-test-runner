pipeline {
    agent any

    parameters {
        choice choices: ['login', 'smoke', 'regression', 'faker'], name: 'TEST_TARGET'
    }

    stages {

        stage('Run Test') {
            steps {
                sh "docker-compose up"
            }
        }
    }

    post {
        always {
            sh "docker-compose down"
            archiveArtifacts artifacts: 'reports/*.html, reports/*.json', followSymlinks: false
        }
    }
}