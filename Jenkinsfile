pipeline {
  agent {
    kubernetes {
      // We cloud, Jenkins will pick the first cloud in the list
      cloud "kubernetes"
      label "jenkins"
      yamlFile "jenkins/jenkins-build-pod.yaml"
    }
  }
  stages {
    stage("Build"){
      steps{
         container("kubectl") {
             sh "kubectl get pods"
          }
      }
    }
  }

}