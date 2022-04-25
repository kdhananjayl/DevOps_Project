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
          //deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://3.230.51.153:8080')], contextPath: '', onFailure: false, war: '**/*.war' 
          //deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://3.230.51.153:8080')], onFailure: false, war: '**/*.war'
          //deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://3.230.51.153:8080')], war: '**/*.war'
          //deploy adapters: [tomcat9(credentialsId: 'tomcat', path: '', url: 'http://3.230.51.153:8080')], contextPath: null, war: '**/*.war'
          deploy adapters: [tomcat9(credentialsId: 'tomcatnew', path: '', url: 'http://3.230.51.153:8080')], contextPath: null, war: '**/*.war'
        }
      }
    }
  }
}
