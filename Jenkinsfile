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
    stage ('Nexus upload') {
      steps {
        echo 'Nexus Uploader....'
        nexusArtifactUploader artifacts: [[artifactId: 'app', classifier: '', file: 'target/app-1.0.0.4.war', type: 'war']], credentialsId: 'nexus3', groupId: 'com.mithun', nexusUrl: '54.90.181.192:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'jenkins', version: '1.0.0.4'     
      }
    }    
    stage ('Deploy') {
      steps {
        script {
          deploy adapters: [tomcat9(credentialsId: 'tomcat-latest', path: '', url: 'http://3.230.51.153:8080')], onFailure: false, war: '**/*.war'
        }
      }
    }
  }
}
