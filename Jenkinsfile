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
            echo "Print driverpath ${ChromeDriverPath}"
          }
        }

        stage('Create file') {
          steps {
            writeFile(file: 'testlog.txt', text: 'Writing a file')
          }
        }

      }
    }

    stage('Deploy') {
      parallel {
        stage('Deploy') {
          steps {
            input(message: 'Do you want to deploy?', id: 'Yes')
            echo 'Deploy it to cloud'
          }
        }

        stage('Artifact') {
          steps {
            archiveArtifacts 'Logte'
            archiveArtifacts 'testlog.txt'
          }
        }

      }
    }

  }
  environment {
    ChromeDriverPath = 'C:/Driver/Chrome'
  }
}