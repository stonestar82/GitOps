pipeline {
  agent any
  stages {
    stage('git pull') {
      steps {
        // https://github.com/stonestar82/GitPos.git will replace by sed command before RUN
        git url: 'https://github.com/stonestar82/GitPos.git', branch: 'main'
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