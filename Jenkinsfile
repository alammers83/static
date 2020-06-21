pipeline {
    agent any
    stages {
        stage('Lint HTML') {
            steps {
                sh 'echo Linting HTML'
                sh 'tidy -q -e *.html'
            }
        }
        stage('Upload to AWS') {
            steps {
                retry(3) {
                    withAWS(region:'us-east-1', credentials: 'aws-static') {
                        s3Upload(file:'index.html', bucket:'jenkins-pipe', path:'index.html')
                    }
                }
            }
        }
        stage('Health check') {
            steps {
                sh 'curl --silent --fail "http://jenkins-pipe.s3-website.us-east-1.amazonaws.com" >/dev/null'
            }
        }
    }
}
