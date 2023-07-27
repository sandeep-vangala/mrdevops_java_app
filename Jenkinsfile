pipeline {
    agent any 
    stages {
        stage ('git checkout') {

            steps{

                script {

                    gitCheckout(
                        branch: "sample"
                        url: "https://github.com/sandeep-vangala/mrdevops_java_app.git"
                    ) 

                    
                }
                
            }
        }
    }
}
