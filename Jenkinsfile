pipeline {
	agent any
	
	stages {
		stage ("Install Dependencies") {
			
		steps {
			nodejs('node') {
                        sh 'npm install '
                    	}
			}
			}
        
        
        stage ("Build App") {
            steps {
                nodejs('node') {
                
                    sh 'npm run build'
                }
            	}
        	} 

        stage ("Deploy to server") {
            steps {
                sshagent(['server-id']) {
                
                    sh 'rsync -rvu * ubuntu@ipaddress:~'
                }
            
            	}
        
        	}    
        	}
}	
