node {
    def app

    stage('Clone repository') {
       checkout scm 
    } 

    stage('Build image') {
       app = docker.build('claudita/example-app')
    }

    stage('Push image') {
       docker.withResgistry('https://registry.hub.docker.com', 'docker-hub-credentials'){
          app.push('latest')
       }
    } 
}
