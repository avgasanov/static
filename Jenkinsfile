pipeline {
	agent any
	stages {
	   stage('Upload to AWS') {
		   steps {
			   withAWS(region:'us-east-1', credentials:'aws-static') {
				   s3Upload(pathStyleAccessEnabled:true, payloadSigningEnabled: true, file:'index.html', bucket:'jenkins-01')
		   		}
	   		}
	   }
	   stage('Lint HTML') {
	            steps {
		           sh 'tidy -q -e *.html'
	            }
	   }
	}
}
