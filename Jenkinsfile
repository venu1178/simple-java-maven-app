pipeline {
  agent {
    kubernetes {
      // Without cloud, Jenkins will pick the first cloud in the list
      cloud "kubernetes"
      yamlFile "jenkins/jenkins-build-pod.yaml"
    }
  }
   stages {
     stage("Deploy") {
           steps {
             container("kubectl") {
               sh """cat <<EOF | kubectl apply -f -
     apiVersion: apps/v1
     kind: Deployment
     metadata:
       name: order-service
     spec:
       replicas: 2
       selector:
         matchLabels:
           app: order-service
       template:
         metadata:
           labels:
             app: order-service
         spec:
           containers:
           - name: order-service
             image: gcr.io/fsi-retailbanking-dev/order-service:v1
     """
               sh "kubectl rollout status deployments/hello-app"
             }
           }
         }
       }
     }