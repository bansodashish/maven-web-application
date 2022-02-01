node
{
  def mavenHome=tool name: "maven"
  
  stage('Checkout')
 {
 	git branch: 'development', credentialsId: 'bed5a851-d84d-412e-87e7-bf9ce23c0e0e', url: 'https://github.com/MithunTechnologiesDevOps/maven-web-application.git'
 
 }
 
 stage('Build')
 {
 sh  "${mavenHome}/bin/mvn clean package"
 }
 
 stage('DeployAppintoTomcat')
 {
 sshagent(['cd93d61f-2d0f-4c60-8b33-34cf4fa888b0']) {
  sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@13.235.132.183:/opt/apache-tomcat-9.0.29/webapps/"
 }
 }

 }
