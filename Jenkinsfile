pipeline {
    agent {
        label 'centos'
    }
    stages {
        stage('Example') {
            steps {
                withDockerRegistry([ credentialsId: "7404298959", url: "" ]) {
                    sh 'docker build -f Dockerfile-prod -t 7404298959/reacthub:react-app .'
                    sh 'docker push 7404298959/reacthub:react-app'
                }
                    sh 'docker pull 7404298959/reacthub:react-app && docker run -d --name react-app -p 80:80 7404298959/reacthub:react-app'
                    sh 'docker ps'
            }
        }
    }
}
