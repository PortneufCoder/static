pipeline {
    agent any
    stages {
        stage('Upload to AWS') {
            steps {
                withAWS(credentials: 'aws-static', region: 'us-west-2') { 
                s3Upload(file: 'index.html', bucket: 'project03bucket', path: 'index.html')
                sh 'echo "Uploading index.html'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
                }
            }
        }
    }
}