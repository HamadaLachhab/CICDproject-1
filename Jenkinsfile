pipeline{
   agent any 
    stages{
        stage("Sonar Quality Check"){
            agent{
                docker {
                    image 'openjdk:11'
                }
            }
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'sonar-token') {
                        sh 'chomd +x gradlew'
                        sh './graldlew sonarqube/'
                    }
                }
            }
            
        }
    }
    post{
        always{
            echo "SUCCESS"
        }
        
    }
}