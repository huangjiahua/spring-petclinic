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
        sh 'mvn sonar:sonar -Dsonar.projectKey=org.springframework.samples:spring-petclinic -Dsonar.host.url=http://localhost:9000 -Dsonar.login=b0b4e4adfcb6f18f4b6f30623ce56ea9c8a44b63'
      }
    }

    stage('deploy') {
      steps {
        sh 'cp /home/vagrant/deploy.yml ./deploy-playbook.yml && ansible-playbook --user=vagrant deploy-playbook.yml ; rm deploy-playbook.yml'
      }
    }

  }
}