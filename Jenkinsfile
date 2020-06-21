
pipeline {
  agent any 
  stages {
    stage('Lint HTML') {
        steps {
            sh 'tidy -q -e index.html'
   }
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

