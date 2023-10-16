node {
     stage('Clone repository') {
         checkout scm
     }
     stage('Build image') {
         app = docker.build("2017301050@skuniv.ac.kr/flask-example")
         
     }
     stage('Push image') {
         docker.withRegistry('https://registry.hub.docker.com', 'docker-hub') {
             app.push("${env.BUILD_NUMBER}")
             app.push("latest")
         }
     }
}
