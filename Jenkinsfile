pipeline {
  agent any
  stages {
    stage('git pull') {
      steps {
        // git@github.com:yyc9920/GitOps.git will replace by sed command before RUN
        git url: 'git@github.com:yyc9920/GitOps.git', branch: 'main'
      }
    }
    stage('k8s deploy'){
      steps {
        kubernetesDeploy(kubeconfigId: 'kubeconfig',
                         configs: '*.yaml')
      }
    }    
  }
}