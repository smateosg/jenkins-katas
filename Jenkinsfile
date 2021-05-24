pipeline {
  agent {
    docker {
      image 'gradle:jdk11'
    }

  }
  stages {
    stage('Parallel execution') {
      steps {
        sh 'echo "Parallel execution"'
      }
    }

    stage('Compilar aplicacion') {
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