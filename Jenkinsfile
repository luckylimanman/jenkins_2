pipeline {
    agent {
        label '!windows'
    }

    environment {
        DISABLE_AUTH = 'true'
        DB_ENGINE    = 'sqlite'
    }

    stages {
        stage('Prepare') {
            steps {
                git branch: main, url: 'https://gitlab.cee.redhat.com/cplabstests/e2e.git'
                }
        }
        stage('Build') {
            steps {
                sh '''
                npm install
                node index.js
                '''
            }
        }
    }
    post {
        failure {
        mail to: 'mandli@redhat.com',
             subject: "jenkins learn fail",
             body: "Something is wrong"
    }
    }
}