node
{
	stage('SCM Checkout')
	{
		git 'https://github.com/reddy2018/mvn_SHtechnology.git'
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
			sh 'scp -o StrictHostKeyChecking=no target/*.war ec2-user@172.31.95.192:/opt/tomcat/apache-tomcat-9.0.10/webapps/'
      		}
	}
}
