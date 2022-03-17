pipeline{
    agent any 
    tools{
        maven 'maven3'
    }
    stages{
        stage("checkout"){
            steps{
                git url:  "https://github.com/Ranjit1709/biojava.git" ,branch: 'master', credentialsId: 'ranjit1709'
            }
        }
        
       stage("Sonarqube Analysis"){
           steps{
                sh 'mvn verify org.sonarsource.scanner.maven:sonar-maven-plugin:sonar -Dsonar.projectKey=Biodata'
           }
           
       }
       stage("build"){
        steps{
            sh 'mvn  -Dmaven.test.skip=true package'
        }
       }
        
    }
    
    
}