pipeline {
    agent any 
    stages {
        stage ('git checkout') {

            steps{

                script {

                    git branch: 'sample', url: 'https://github.com/sandeep-vangala/mrdevops_java_app.git'

                    
                }
                
            }
        }
    }
}
