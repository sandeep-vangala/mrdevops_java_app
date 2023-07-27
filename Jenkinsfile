@Library('my-shared-library') _

pipeline {
    agent any 
    parameters {

        choice(name: 'action', choices: 'create\ndelete', description: 'choose create/Destroy')

    }
    stages {
        
        stage ('git checkout') {
        when { expression {params.action == 'create'} }
            steps{

                script {

                    gitCheckout(
                        branch: "sample",
                        url: "https://github.com/sandeep-vangala/mrdevops_java_app.git"
                    ) 

                    
                }              
            }     
        }

        stage ('unit test maven') {
            steps{

                script {

                    mvnTest()

                }   
            }
        }

        stage ('maven integration test') {
            steps{

                script {

                    mvnIntegrationTest()
                }
            }
        }

       /* stage ('static code analysis: sonarQube') {
            steps{

                script {

                    def SonarQubecredentialsId = 'sonar-api'
                    staticCodeAnalysis(SonarQubecredentialsId)
                }
            }
        }   */             
    }
}

