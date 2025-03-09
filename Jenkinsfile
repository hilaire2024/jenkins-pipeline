pipeline {
   agent any
   stages{
    stage('Codescan'){
        steps{
            sh 'trivy --version'
        }
    }
    stage('dockerImageBuild'){
        steps{
            sh 'docker -v'
        }
}
    stage('pushImage'){
        steps{
            sh 'docker ps'
        }
    }
   } 

}