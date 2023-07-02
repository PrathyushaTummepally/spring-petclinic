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
  -Dsonar.projectName=\'Petclinic\' \\
  -Dsonar.host.url=http://65.2.36.5:9000 \\
  -Dsonar.token=sqp_b1fa0a5607e2bb48903764710aa5e7b9addd2f0d'''
      }
    }

  }
}