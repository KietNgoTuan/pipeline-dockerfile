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
			    }
        }
            steps{
		script {
			docker.withRegistry('https://index.docker.io/v2/', '${env.DOCKER_HUB_CRED}') {
		       		def app = docker.build("kiettheo98/pipline-docker-test", '.').push("${env.BRANCH_NAME}")
	       		}
		}
               
            }
        }
    }
}
