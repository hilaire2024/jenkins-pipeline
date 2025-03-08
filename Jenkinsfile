pipeline {
    agent any
    stages {
        stage('clone'){
            stepes{
                sh 'echo "clone"'
            }
        }
        stage('test'){
            steps{
                sh 'echo "test"'
            }
        }
        stage('createfile'){
            steps{
                sh 'touch text-$BUILD_ID'
            }
        }
    }  

}