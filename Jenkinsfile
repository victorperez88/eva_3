
pipeline {
  agent any
  options { timestamps(); ansiColor('xterm') }
  stages {
    stage('Checkout'){ steps { checkout scm } }
    stage('Build'){ steps { sh 'mvn -B -DskipTests package' } }
    stage('Unit Tests'){ steps { sh 'mvn -B -DskipITs test' } post { always { junit 'target/surefire-reports/*.xml' } } }
    stage('Integration Tests'){ steps { sh 'mvn -B verify' } post { always { junit 'target/failsafe-reports/*.xml' } } }
  }
  post { success { echo 'CI SUCCESS' } failure { echo 'CI FAILED' } }
}
