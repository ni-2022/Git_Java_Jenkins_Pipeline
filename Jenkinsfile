pipeline {
    agent any

    tools {
        maven "MAVEN_HOME"
        jdk "JAVA_HOME"
    }

    stages {
        stage('Initialize'){
            steps{
                echo "PATH = ${M2_HOME}/bin:${PATH}"
                echo "M2_HOME = /opt/maven"
            }
        }
        stage('Build') {
            steps {                
                dir ("C:/ProgramData/Jenkins/.jenkins/workspace/Java_Maven_Pipeline/")
                    {
                    sh 'mvn -B -DskipTests clean package'
                    }
            
            }
        }
     }
    post {
       always {
          junit(
        allowEmptyResults: true,
        testResults: '*/test-reports/.xml'
      )
      }
   } 
}
