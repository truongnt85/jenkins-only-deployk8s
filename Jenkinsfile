pipeline {

  agent { label 'kubepods' }

  stages {

    stage('Checkout Source') {
      steps {
        git url:'https://github.com/truongnt85/jenkins-only-deployk8s.git', branch:'master'
      }
    }

    stage('Deploy App') {
      steps {
        script {
          kubernetesDeploy(configs: "nginx.yaml", kubeconfigId: "Fintech-kubeconfig")
          kubernetesDeploy(configs: "nginx-deploy-blue.yaml", kubeconfigId: "Fintech-kubeconfig")
          kubernetesDeploy(configs: "nginx-deploy-green.yaml", kubeconfigId: "Fintech-kubeconfig")
        }
      }
    }

  }

}
