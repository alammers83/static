pipeline {
  agent any 
  stages {
  stage ('Upload to AWS') {
    steps {
      sh 'echo "Hello World"'
      sh '''
        echo "Multiline shells steps works too"
        ls -lah
      '''
      }
    }
  }
}


