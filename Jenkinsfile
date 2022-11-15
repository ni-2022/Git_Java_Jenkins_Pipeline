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
                dir ("F:/Bolton_University/DevOps/Others/Naveed_Islam_Lectures/Weekwise_Lectures/CI_CD_Jenkins/jenkins-pipeline-example-main/jenkins-pipeline-example-main/my-app/")
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
