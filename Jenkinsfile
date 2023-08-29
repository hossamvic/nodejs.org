pipeline {
    agent any

    stages {
       stage('Checkout') {
            steps {
                checkout scm
            }
        }
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

        // Add more stages as needed
    }
}


