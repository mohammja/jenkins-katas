pipeline {
  agent any
  stages {
    stage('Parallel execution') {
      parallel {
        stage('SayHello') {
          steps {
            sh 'echo "Hello World!"'
          }
        }

        stage('build app') {
          agent {
            docker {
              image 'gradle:6-jdk11'
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