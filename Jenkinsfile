pipeline {
  agent any
  stages {
    stage('BUILD') {
      steps {
        sh 'touch file1'
      }
    }

    stage('Test') {
      parallel {
        stage('Test') {
          steps {
            build(job: 'job-111', propagate: true, quietPeriod: -8, wait: true)
          }
        }

        stage('') {
          steps {
            sh 'touch abc'
          }
        }

      }
    }

  }
}