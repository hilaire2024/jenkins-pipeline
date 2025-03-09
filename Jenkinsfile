pipeline {
   agent any
   stages{
    stage('Codescan'){
        steps{
            sh 'trivy fs . -o results.html'
            sh 'cat results.html'
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