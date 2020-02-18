pipeline {
    agent any
    stages {
        stage('Lint HTML'){
            steps {
                sh 'tidy -q -e *.html'
            }
        }
        stage('Upload to AWS') {
            steps {
                withAWS(credentials: 'aws-static', region: 'us-west-2') { 
                s3Upload(file: 'index.html', bucket: 'project03bucket', path: 'index.html')               
                sh '''
                    echo "Uploading index.html with AWS creds"
                    echo "Copy file to S3"
                    ls -lah
                '''
                }
            }
        }
    }
}