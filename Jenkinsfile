/*pipeline {
    agent any
    environment {
        PROJECT_ID = 'fsi-retailbanking-dev'
        CLUSTER_NAME = 'ordermanagment-cluster'
        LOCATION = 'us-central1'
        CREDENTIALS_ID = 'fsi-retailbanking-dev'
    }
    stages {
        stage('Deploy to GKE') {
            steps{
                step([
                $class: 'KubernetesEngineBuilder',
                projectId: env.PROJECT_ID,
                clusterName: env.CLUSTER_NAME,
                location: env.LOCATION,
                manifestPattern: 'jenkins/maven-pod.yaml',
                credentialsId: env.CREDENTIALS_ID,
                verifyDeployments: true])
            }
        }
    }
}*/

/*pipeline {
    agent any
    stages {
        stage('Deploy') {
            steps {
                 agent {
                     kubernetes {
                         label 'mavenpod'
                         yamlFile 'jenkins/maven-pod.yaml'
                       }
                   }
                   container('maven') {
                   sh "mvn -B clean deploy"
                 }
            }
        }
    }
}*/

  tools {
   jdk 'jdk-11'
   maven 'mvn-3.6.3'
  }

  stages {
   stage('Build') {
    steps {
     withMaven(maven : 'mvn-3.6.3') {
      sh "mvn package"
     }
    }
   }

