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
pipeline {
    agent any
     tools {
       jdk 'java'
       maven 'maven'
      }
    stages {
        stage('Deploy') {
            steps {
                container('maven') {
                  sh "mvn -B clean deploy"
                }
            }
        }
    }
}

