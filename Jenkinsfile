pipeline {
  agent any
  stages {
    stage('test') {
      steps {
        sh 'docker run --rm -v ${WORKSPACE}:/app_python -w /app_python imagem_python:tag python test.py'
      }
      post {
        always {
          junit 'test-reports/*.xml'
        }
      }    
    }
    stage('Run App') {
      sh 'docker run -d'
    }
  }
}
