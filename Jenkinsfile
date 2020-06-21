pipeline {
  agent any 
  stages {
  stage ('Build') {
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


