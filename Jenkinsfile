pipeline {
    agent any
    environment {
     DEPLOY_TO = "Production" 
     JOB_TIME = sh (returnStdout: true; script:"date '+%A %W %Y %X'").trim()
        
        
    }
    tools {
     maven 'MAVEN'   
        
    }

    stages {
        
       
        stage ("Welcome stage") {
            steps {
                     bat "echo welcome stage "   
            }
            
        }
        stage ("Initialization") {
            steps {
                echo "${BRANCH_NAME}"
                echo "${DEPLOY_TO}"
            }
            
        }
        stage ("Load tools") {
            steps {
              bat "mvn -version"

            }   
        }
        stage ('Compile Stage') {

            when {
              branch   'feature-1'       
            }
            steps {
           
                 echo "hello from feature-1 branch"
                }
            }
        }

        post {
         always {
             echo "You can always see me"
         }
         success {
              echo "I am running because the job ran successfully"
         }
         unstable {
              echo "Gear up ! The build is unstable. Try fix it"
         }
         failure {
             echo "OMG ! The build failed"
         }
     }
    
}
