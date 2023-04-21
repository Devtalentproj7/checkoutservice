pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'go build'
      }
    }

    stage('SonarQube Analysis') {
      steps {
        sh '''sonar-scanner \\
  -Dsonar.projectKey=checkoutservice \\
  -Dsonar.sources=. \\
  -Dsonar.host.url=http://172.31.13.141:9000 \\
  -Dsonar.token=sqp_0624f352bbd247a97d1dc53b9ca331e9f9f5292f'''
      }
    }

  }
}