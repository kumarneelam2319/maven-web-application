node
{
 def mavenHome = tool name: "maven3.9.5"     
 stage('checkout')
 {
 git credentialsId: '8d8cda8c-1444-48df-9056-5050603b7880', url: 'https://github.com/kumarneelam2319/maven-web-application'
 }
 stage('build')
 {
 sh "${mavenHome}/bin/mvn clean package"
 }
 stage('sonarqubeserver')
 {
 sh "${mavenHome}/bin/mvn clean package sonar:sonar"   
 }
 stage('nexus')
 {
 sh "${mavenHome}/bin/mvn clean package deploy"     
 }
/*  
 stage('mail')
 {
 mail bcc: '', body: 'thanks', cc: '', from: '', replyTo: '', subject: 'Build over', to: 'sivaram2319@gmail.com'    
 }
*/ 
} 
