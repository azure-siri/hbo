properties([parameters([
    string(defaultValue: '', description: "artifcat complete name", name: 'artifactName', trim: true),
    string(defaultValue: '', description: "s3 folder name", name: 'path', trim: true),
    string(defaultValue: '', description: "artifcat version", name: 'version', trim: true),
    string(defaultValue: '', description: "enter the repo name", name: 'assetRepoName', trim: true)
	
])])

def configMap = [
     'assetRepoName': assetRepoName,
	 'version': version,
	 'artifactName': artifactName,
	 'path': path
]


s3Upload configMap


