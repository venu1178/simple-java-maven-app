pipeline {
    agent none
    tools {
            // Install the Maven version configured as "M3" and add it to the path.
            maven "maven"
            jdk "java"
    }
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
}
