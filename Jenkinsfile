pipeline {
	agent any
	tools {nodejs "LastestNode"}
	stages {
		stage('install npm packages') {
			steps {
				bat 'npm install'
			}
		}		
		stage('Build project') {
			steps {
				bat 'npm run build'
			}
		}
		
		stage('Deploy to IIS') {
			steps {
				bat 'Xcopy build C:\\inetpub\\wwwroot\\ReactDevOpsExp5 /E /H /C /I /Y'
				
				// /E Copies all subdirectories, even if they're empty. 
				// /H Copies files with hidden and system file attributes. 
				// /C Ignores errors.
				// /I Use the /i option to force xcopy to assume that destination is a directory.
				// /Y is yes to all prompts
			}
		}
	}
}