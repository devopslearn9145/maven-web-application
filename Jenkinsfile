node 
{
    def MavenHome = tool name: "maven-3.8.6"
    
    properties([pipelineTriggers([pollSCM('* * *  * *')])])
    
    stage ('CheckoutCode')
    {
        git branch: 'development', credentialsId: 'c4184b64-e2cf-47aa-99ff-cea26767ff82', url: 'https://github.com/devopslearn9145/maven-web-application.git'
    }
    
    stage ('Build')
    {
        sh "$MavenHome/bin/mvn clean package"
    }
    
  /*
    stage ('ExecuteSonarQubeReport')
    {
        sh "$MavenHome/bin/mvn sonar:sonar"
    }
    
    stage ('DeployArtifactintoNexus')
    {
    sh "$MavenHome/bin/mvn deploy"    
    }
    
    stage ('DeployintoTomcatServer')
    {
        sshagent(['411bb23f-d536-49ca-bd9e-8d6a32895377']) {
   sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@54.163.208.183:/opt/apache-tomcat-9.0.69/webapps/"
}
    }
    
    */
}

