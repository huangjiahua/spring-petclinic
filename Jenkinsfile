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
        sh 'mvn sonar:sonar -Dsonar.projectKey=org.springframework.samples:spring-petclinic -Dsonar.host.url=http://localhost:9000 -Dsonar.login=14bb09599f62775efce8c5ebebdace2f8c7b4ccb'
      }
    }

    stage('start') {
      steps {
        sh 'java -jar target/*.jar'
      }
    }

  }
}