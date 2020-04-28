pipeline {
    agent any
    stages {
        stage('Upload to AWS') {

            withAWS(region:'us-east-1', credentials:'aws-creds') {
                s3Upload(file:'index.html', bucket:'jenkins-code', path:'')
            }

        }
    }
}