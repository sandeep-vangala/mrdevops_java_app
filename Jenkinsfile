@Library('my-shared-library') _

pipeline {
    agent any 
    parameters {

        choice(name: 'action', choices: 'create\ndelete', description: 'choose create/Destroy')

    }
    stages {
        when { expression { params.action == 'create'} }
        stage ('git checkout') {

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
         when { expression { params.action == 'create'} }

            steps{

                script {

                    mvnTest()

                }   
            }
        }

        stage ('maven integration test') {
         when { expression { params.action == 'create'} }
            steps{

                script {

                    mvnIntegrationTest()
                }
            }
        }

        stage ('static code analysis: sonarQube') {
         when { expression { params.action == 'create'} }
            steps{

                script {

                    staticCodeAnalysis()
                }
            }
        }                
    }
}

