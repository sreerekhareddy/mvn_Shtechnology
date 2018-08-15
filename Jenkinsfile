node
{
	stage('SCM Checkout')
	{
		git 'https://github.com/sreerekhareddy/mvn_Shtechnology.git'
	}
	stage('Compile-Package'){
		// Get maven home path
      		def mvnHome =  tool name: 'maven 3.5.4', type: 'maven'   
     		sh "${mvnHome}/bin/mvn package"
	}
	
}
