node ('master')
{
    def mavenHome = tool name: "mvn-3.6.2"
    properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), pipelineTriggers([pollSCM('* * * * *')])])	
    stage ('CodeGet')
    {
     git branch: 'development', credentialsId: '4982db24-6753-4bcd-85b0-501967e905a0', url: 'https://github.com/surisharma/maven-web-application.git'
    }
    stage ('Build')
    {
    sh "${mavenHome}/bin/mvn clean package"
    }
	/*stage ('ExcuteSonar')
	{
	sh "${mavenHome}/bin/mvn sonar:sonar"
	}
	stage ('UploadArtifact')
	{
	sh "${mavenHome}/bin/mvn deploy"
	}
	stage ('DeployCode')
	sshagent(['f354e9d4-93ba-45d2-93a9-beef3755bb4a'])
	{
	sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@54.210.242.7:/opt/apache-tomcat-9.0.63/webapps"
	}
	stage ('EmailNotification')
	{
	mail bcc: '', body: '''Please check the Build.
    Regards,
    Surinder''', cc: '', from: '', replyTo: '', subject: 'Build Completed', to: 'surinder280@gmail.com'
    } */
}
