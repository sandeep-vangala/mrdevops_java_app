@Library('my-shared-library') _

pipeline {
    agent any 
    tools {
        maven maven-3.9.3
    }
    stages {
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

            steps{

                script {

                    mvnTest()

                }
                
            }
        }    
    }
}

