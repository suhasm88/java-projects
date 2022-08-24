pipeline {
    agent any
     environment{
        VERSION = "${env.BUILD_ID}"
    }
    stages{
        stage("sonar quality check"){
            agent {
            docker {
                image 'maven:latest'
                }
        }
             steps{
                script{
                    withSonarQubeEnv(credentialsId: 'b297ab87-6860-4214-aee9-b833d1302efc') {
                        sh 'mvn clean install'

                    }

                }
            }
        }
    }
}
