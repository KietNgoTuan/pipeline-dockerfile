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
		sh 'docker login -u kiettheo98 -p Kiettheo98 https://index.docker.io/v2/'    
		script {
			       docker.withRegistry("https://hub.docker.com", "${params.myCredentials}") {
		       		def app = docker.build("kiettheo98/pipline-docker-test", '.').push("${env.BRANCH_NAME}")
			       }
		}
               
            }
        }
    }
}
