
pipeline {
  agent any 
  stages {
    stage ('Upload to AWS') {
     steps {
        withAWS(region:'us-east-1',credentials:"aws-static") {
           s3Upload(file:'index.html', bucket:'jenkins-pipe', path:'index.html')
    }

      sh 'echo "Hello World"'
      sh '''
        echo "Multiline shells steps works too"
        ls -lah
          '''
      }
    }
  }
}

