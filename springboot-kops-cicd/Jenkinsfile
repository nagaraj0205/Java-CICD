pipeline {
 agent any
 stages {
  stage('Build'){ steps { sh 'mvn clean package' } }
  stage('Docker'){ steps { sh 'docker build -t app:$BUILD_NUMBER .' } }
  stage('Deploy'){ steps { sh 'kubectl rollout restart deployment/springboot-app' } }
 }
}