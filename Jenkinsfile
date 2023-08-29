pipeline { 
  
   agent any

   stages {
   
     stage('Install Dependencies') { 
        steps { 
           sh 'npm install' 
        }
     }
     
     stage('Test') { 
        steps { 
           sh 'echo "testing application..."'
        }
      }

        stage('Build') {
            steps {
                // Build your application
                 sh 'npm run build'
            }
        }

  
   	}

   }
