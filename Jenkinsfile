node('nodes')
{
  def mavenHome = tool name: "maven 3.6.2"
  properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), pipelineTriggers([pollSCM('* * * * *')])])
  stage ('CheckouCode')
  {
    git branch: 'development', credentialsId: '5b3a7865-20e9-4521-9fa9-85c9541a863a', url: 'https://github.com/surisharma/maven-web-application.git'
  }
  stage ('Build')
  {
   sh "${mavenHome}/bin/mvn clean package"   
  }
  /* 
  stage ('Code tesing')
  {
  sh "${mavenHome}/bin/mvn sonar:sonar"
  }
  stage ('UploadartifactintoNexus')
  {
   sh "${mavenHome}/bin/mvn deploy"
   }
   */
   stage ('Deployment')
   {
   sshagent(['1facf916-ccc4-4cda-83e5-3057bf6f914b'])
   {
    sh "scp -o  StrictHostKeyChecking=no target/maven-web-application.war ec2-user@13.235.83.62:/opt/apache-tomcat-9.0.53/webapps"     
    }   
    }
   /* 
   stage ('Mail Notifucation')
    {
        mail bcc: '', body: 'Bulid deploy', cc: '', from: '', replyTo: '', subject: 'Build Sucess', to: 'surinder280@gmail.com'
    }
    */
}
  
