pipeline {
    agent {label 'maven'}
environment {
    PATH = "/opt/apache-maven-3.9.4/bin:$PATH"
}
    stages {
       stage("build"){
         steps {
              sh 'mvn clean deploy'
            }
       }
    
    
       stage("test"){
         steps {
              sh 'mvn surefire-report:report'
            }
       }
    
    
        

        stage("SonarQube"){
            environment{
             scannerHome = tool 'demo_scanner'
            }
         steps {
              withSonarQubeEnv('project_demo_cicd'){
                sh "${scannerHome}/bin/sonar-scanner"
              }
            }
        }   
    }
}
