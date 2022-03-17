pipeline {
	  agent none
    stages {        
        stage('Build'){   
		    agent {
			    dockerfile {
				    dir 'dockerfileDir'
			    }
        }
            steps{
                sh 'dotnet --version'
	        // run with node image
		sh 'node --version'    
            }
        }
    }
}
