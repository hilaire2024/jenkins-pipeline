pipeline {
   agent any
   stages{
    stage('Codescan'){
        steps{
            sh 'trivy fs . -o results.html'
            sh 'cat results.html'
        }
    }
    stage(dockerLogin){
        steps{
            sh 'aws ecr get-login-password --region us-east-1 |\
             docker login --username AWS \
             --password-stdin 039612886015.dkr.ecr.us-east-1.amazonaws.com'
        }
    }
    stage('dockerImageBuild'){
        steps{
            sh 'docker build -t jenkins-ci .'
        }
}
    stage('dockerImageTag'){
        steps{
            sh 'docker tag jenkins-ci:latest 039612886015.dkr.ecr.us-east-1.amazonaws.com/jenkins-ci:latest'
        }
    }
    stage('pushImage'){
        steps{
            sh 'docker push 039612886015.dkr.ecr.us-east-1.amazonaws.com/jenkins-ci:latest'
            
        }
    }
   } 

}