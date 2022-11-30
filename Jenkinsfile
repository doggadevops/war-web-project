pipeline {
    agent any
    environment {
       REPO_URL="https://github.com/doggadevops/war-web-project"
    }
    stages{
        stage("checkout") {
            steps{
                cleanWs()
                sh 'printenv'
                sh "git clone ${REPO_URL} "
            }
        }
        stage("build code"){
            steps{
                script{
                    sh """
                    ls -lrt
                    cd war-web-project
                    mvn install
                    """
                }
            }
        }
        stage("Run Unit Test"){
            steps{
                script {
                    sh """
                    cd war-web-project
                    mvn test
                    """
                }
            }
        }
    }
}
