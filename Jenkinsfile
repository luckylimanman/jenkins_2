pipeline {
    agent any

    // environment {
    //     DISABLE_AUTH = 'true'
    //     DB_ENGINE    = 'sqlite'
    // }

    stages {
        // stage('Prepare') {
        //     steps {
                
        //         }
        // }
        stage('Build') {
            steps {
                // git branch: main, url: 'https://gitlab.cee.redhat.com/cplabstests/e2e.git'
                // sh '''
                // npm install
                // node index.js
                // '''
                sh 'echo "Hello World"'
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