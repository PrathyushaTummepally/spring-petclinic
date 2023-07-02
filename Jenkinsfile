pipeline {
  agent {
    node {
      label 'test'
    }

  }
  stages {
    stage('Compile') {
      steps {
        sh './mvnw clean compile'
      }
    }

    stage('Static Analysis') {
      steps {
        sh '''./mvnw clean verify sonar:sonar \\
  -Dsonar.host.url=http://172.31.31.57:9000 \\
  -Dsonar.projectKey=Petclinic \\
  -Dsonar.token=sqp_d98e5efdface650b409cd56cb66ea28b52e7be18'''
      }
    }

  }
}