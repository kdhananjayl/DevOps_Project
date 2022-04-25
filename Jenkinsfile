pipeline {
  agent any
  tools {
    maven 'maven' 
  }
  stages {
    stage ('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage ('Deploy') {
      steps {
        script {
          //deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://3.94.176.67:8080')], contextPath: '', onFailure: false, war: '**/*.war' 
          deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://3.94.176.67:8080')], onFailure: false, war: '**/*.war'
        }
      }
    }
  }
}
