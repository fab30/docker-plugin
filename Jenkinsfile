// Jenkinsfile
pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        parallel(
          "Build": {
            echo 'hello'
            
          },
          "Build other": {
            pwd(tmp: true)
            
          }
        )
      }
    }
    stage('Test') {
      steps {
        parallel(
          "Chrome": {
            echo 'testing in chrome'
            
          },
          "Firefox": {
            echo 'testing in firefox'
            
          },
          "dds": {
            echo 'tested'
            
          }
        )
      }
    }
    stage('Deploy') {
      steps {
        echo 'deploying'
      }
    }
    stage('finish') {
      steps {
        archiveArtifacts(artifacts: '**/*', allowEmptyArchive: true, caseSensitive: true, defaultExcludes: true)
      }
    }
  }
  environment {
    credential = 'toto'
  }
}
