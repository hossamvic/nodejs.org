pipeline {
  agent any 
    environment{
      CREDENTIALS = credentials('DockerCre')
    }
  stages {
    stage  ("Install dependeincies") {
      agent {
        docker {image 'node:lts-buster-slim'}
      }
      steps {
        sh 'pwd'
        sh 'ls'
        sh 'npm install'
      }
    }
    stage ("Test"){
      agent {
        docker {image 'node:lts-buster-slim'}
      }
      steps{
        sh 'npm run test'
      }
    }
    stage ("Build"){
      agent {
        docker {image 'node:lts-buster-slim'}
      }
      steps{
        sh 'npm run build'
      }
    } 
    stage ("Build Dockerfile") {
      steps{
        sh 'docker build . -t hossamvic/1junkins:latest'
      }
    }
    stage ("login") {
      steps{
        sh 'echo usernamre = ${CREDENTIALS_USR}'
        sh 'echo password = ${CREDENTIALS_PSW}'
        sh 'docker login -u ${CREDENTIALS_USR} -p ${CREDENTIALS_PSW}'
      }
    }

    }

  
}

