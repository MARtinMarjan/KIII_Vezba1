node {
  def app
  stage('Clone repository') {
    chekout scm
  }
  stage('Build image) {
        app = docker.build("MARtinMarjan/KIII_Vezba1")
  }
  stage('Push image){
        docker.withRegistry('https://registry.hub.docker.com', 'dockerhub'){
          app.push("${env.BRANCH_NAME}-${env.BUILD_NUMBER}")
          app.push("${env.BRANCH_NAME}-latest")
        }
  }
}
