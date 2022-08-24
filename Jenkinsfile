pipeline {
    agent any
     environment{
        VERSION = "${env.BUILD_ID}"
    }
    stages{
         stage('Initialize'){
             steps {
        def dockerHome = tool 'myDocker'
        env.PATH = "${dockerHome}/bin:${env.PATH}"
         }
         }
        stage("sonar quality check"){
            agent {
            docker {
                    image 'maven:3.8.1-adoptopenjdk-11'
                     args '-v /root/.m2:/root/.m2'
                        }
        }
             steps {
                script {
                    sh 'mvn clean install'
                    
            }                    


                }
            }
        }
}
