pipeline {

  agent { label 'slave' }

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
        }
      }
    }

  }

}
