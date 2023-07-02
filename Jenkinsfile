pipeline {
  agent any
  stages {
    stage('Compile') {
      steps {
        sh './mvnw clean compile'
      }
    }

    stage('Static Analysis') {
      steps {
        sh '''mvn clean verify sonar:sonar \\
  -Dsonar.projectKey=Petclinic \\
  -Dsonar.host.url=http://172.31.31.57:9000 \\
  -Dsonar.token=sqp_71b85bd5a08134c3ad5b70945e9866dddef150ad'''
      }
    }

  }
}