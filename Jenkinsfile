pipeline {
    agent any
    stages {
        stage('lintHTML') {
            steps {
                sh 'echo "Running the linting tool tidy"'
                sh 'tidy -q -e *.html'
            }
        }

        stage('Upload to AWS') {
            steps {
                sh 'echo "Uploading files to s3 bucket"'
                withAWS(region:'us-east-1', credentials:'aws-creds') {
                    s3Upload(file:'index.html', bucket:'jenkins-code', path:'')
                }
            }
        }
    }
}