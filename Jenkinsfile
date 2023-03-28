node {
        def app
        stage('Clone repo') {
                checkout scm
        }
        stage('Build image') {
          app=docker.build("FilipBosilkov/kiii/tree/master/jenkins")
        }
        stage('Push image') {
                docker.withRegistry('https://registry.hub.docker.com', 'docker') {
                        app.push("${env.BRANCH_NAME}-${env.BUILD_NUMBER}")
                        app.push("${env.BRANCH_NAME}-latest")
                }
        }
}








