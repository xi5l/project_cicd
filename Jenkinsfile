pipeline {
    agent {label 'maven'}
environment {
    PATH = "/opt/apache-maven-3.9.4/bin:$PATH"
}
    stages {
       stage("build"){
         steps {
              echo " ...... build started.........." 
              sh 'mvn clean deploy -Dmaven.test.skip=true'
              echo "..... build completed......"
            }
       }
    }
}
