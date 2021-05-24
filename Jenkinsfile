pipeline {
  agent any
  stages {
    stage('Parallel execution') {
      parallel {
        stage('Hello') {
          agent any
          steps {
            sh 'echo "Hello"'
          }
        }

        stage('Build App') {
          agent {
            docker {
              image 'gradle:6.8.3-jdk11'
            }

          }
          steps {
            sh 'ci/build-app.sh'
          }
        }

      }
    }

  }
}