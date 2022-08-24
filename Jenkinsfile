pipeline {
    agent any
     environment{
        VERSION = "${env.BUILD_ID}"
    }
    stages{
        stage("sonar quality check"){
            agent {
            docker {
                    image 'maven:3.8.1-adoptopenjdk-11'
                     args '-v /root/.m2:/root/.m2'
                        }
        }
             steps {
                script {
                    withSonarQubeEnv(credentialsId: '2f18007b-d594-42e6-bd9a-e096d8ff72f5') {
                       sh 'mvn clean install sonarqube'
                    }
            }                    


                }
            }
        }
}
