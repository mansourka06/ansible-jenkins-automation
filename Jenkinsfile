pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'javac HelloWorld.java'
        sh 'jar cvfe HelloWorld.jar HelloWorld *.class'
      }
    }
    stage('Archive') {
      steps {
        archiveArtifacts artifacts: 'HelloWorld.jar', fingerprint: true
      }
    }
  }
}
