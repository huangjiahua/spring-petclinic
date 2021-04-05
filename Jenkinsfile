pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh 'mvn install'
      }
    }

    stage('analysis') {
      steps {
        sh 'mvn sonar:sonar   -Dsonar.projectKey=org.springframework.samples:spring-petclinic   -Dsonar.host.url=http://localhost:9000   -Dsonar.login=6e0aded3e8eed267ade42fb35589a5c2e959f85d'
      }
    }

    stage('start') {
      steps {
        sh 'java -jar target/*.jar'
      }
    }

  }
}