
pipeline {                                      
    agent  { label 'docker_node_build'}

    environment 
    {
     DOCKERHUB_CREDENTIALS = credentials('docker-hub-login')

    }


    stages {



     
         		
		
		
        stage('BuildDockerImage') {
            steps {                                                  
                echo 'Imageing..'
		sh 'docker build -t deepakkumarawsdevops/newapp:$BUILD_NUMBER .'
		
		
            }
        }
        stage('ReleaseToDockerHub') {                                           
            steps {
                echo 'Releasing....'
		

            }
        }
	stage('LogintoDockerHub')

	{
         steps{
           sh 'echo $DOCKERHUB_CREDENTIALS_PWD | docker login -u $DOCKERHUB_CREDENTIAl_USR --password-stdin'
          	  
	  }



	} 
	stage('Deploy'){

          steps {
             echo 'Deploying...'
	     sh 'docker push deepakkumarawsdevops/newapp:$BUILD_NUMBER'


	       
	              }


	            }

    }                                           

    }
        
