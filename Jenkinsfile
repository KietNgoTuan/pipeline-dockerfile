pipeline {
	  agent none
    stages {        
        stage('Build'){   
		    agent {
          dockerfile true
        }
            steps{
                sh 'dotnet --version'
	        // run with node image
		sh 'node --version'    
            }
        }
    }
}
