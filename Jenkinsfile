pipeline {
    agent any

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