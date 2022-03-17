pipeline {
	  agent none
	environment { 
                DOCKER_HUB_CRED = credentials('dockerhub') 

        }
    stages {        
        stage('Build'){   
		    agent {
			    dockerfile {
				    dir 'dockerfileDir'
				    filename 'test.Dockerfile'
				    registryUrl 'https://index.docker.io/v2/'
				    registryCredentialsId '${env.DOCKER_HUB_CRED}'
			    }
        }
            steps{
		script {
			
		       		def app = docker.build("kiettheo98/pipline-docker-test", '.').push("${env.BRANCH_NAME}")
	       		
		}
               
            }
        }
    }
}
