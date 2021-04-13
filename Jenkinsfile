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
        sh 'mvn sonar:sonar -Dsonar.projectKey=org.springframework.samples:spring-petclinic -Dsonar.host.url=http://localhost:9000 -Dsonar.login=98ee5b2481848a8f0a2eebe3885addd4d2939db2'
      }
    }

    stage('deploy') {
      steps {
        sh 'cp /home/vagrant/deploy.yml ./deploy-playbook.yml && cp /home/vagrant/Dockerfile ./  &&    ansible-playbook deploy-playbook.yml ; rm deploy-playbook.yml'
      }
    }

  }
}