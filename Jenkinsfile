pipeline {
  agent {
    docker {
      image 'gradle6.9:jdk11'
    }

  }
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
              image 'gradle:jdk11'
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