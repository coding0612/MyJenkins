pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'I am building the file'
          }
        }

        stage('Test') {
          steps {
            echo 'I am testing'
          }
        }

      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploy it to cloud'
      }
    }

  }
  environment {
    ChromeDriverPath = 'C:/Driver/Chrome'
  }
}