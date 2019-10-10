String assetRepoName = 'hbo'
String bucketname = 'testbucket-hbo'
//String jenkinsScriptsDir = '/local/jenkins/jenkins-hbo.git/scripts'

pipeline {
    agent any 
    parameters {
            string(name: 'artifactName', description: 'Please enter the artifact name')
            string(name: 'path', description: 'Please enter the s3 folder name')
			string(name: 'version', description: 'Please enter the version')
    }

    stages {
       stage('Check if file exists in S3') {      
            steps {
			  fileExists(artifactName, path)
                
            }
       }
		
	}   
}

 
def fileExists(artifactName, path){
    
	withAWS(credentials:'s3credentials') {
	def result = s3FindFiles bucket: bucketname, path: path, glob: artifactName
	if (result) {
        println "File exists: " + result[0]                       
    } else {
        println "File does not exist fetching from github "
							
      }
	}

}
