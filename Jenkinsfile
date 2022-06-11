node
{
    def mavenHome = tool name: "maven3.6.2"
    stage ('CodeGet')
    {
     git branch: 'development', credentialsId: '97d0edf9-97df-4b6a-a620-3e0d17952ca8', url: 'https://github.com/surisharma/maven-web-application.git'
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
