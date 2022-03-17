pipeline {
	  agent none
	  parameters {							
		
			credentials(name:'myCredentials', description:'myCredentailsDesc', required:true)					
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
			       docker.withRegistry("https://index.docker.io/v2/", "${params.myCredentials}") {
		       		def app = docker.build("kiettheo98/pipline-docker-test", '.').push("${env.BRANCH_NAME}")
			       }
		}
               
            }
        }
    }
}
