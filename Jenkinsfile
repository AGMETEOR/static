pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
            steps {
                sh 'echo "Hello World"'
                sh '''
                echo "Multiline shell steps"
                ls -lah
                '''

            withAWS(region:'us-east-1', credentials:'aws-creds') {
                s3Upload(file:'index.html', bucket:'jenkins-code', path:'')
            }
            }
        }
    }
}