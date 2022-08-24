pipeline {
    agent any
     environment{
        VERSION = "${env.BUILD_ID}"
    }
    stages{
        stage("sonar quality check"){
            agent {
            docker { image 'maven:latest' }
        }
             steps{
                script{
                    withSonarQubeEnv(credentialsId: '2f18007b-d594-42e6-bd9a-e096d8ff72f5') {
                        sh 'maven clean install'
                    }


                }
            }
        }
    }
}
