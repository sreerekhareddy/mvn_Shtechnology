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
	stage('Deploye to tomcat')
	{
		sshagent(['tomcat-dev']) 
		{
			sh 'scp -o StrictHostKeyChecking=no target/*.war ec2-user@13.57.30.81:/usr/share/tomcat/webapps/'
		}
}
}
