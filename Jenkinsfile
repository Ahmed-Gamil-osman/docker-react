pipeline {
    agent {
       label 'docker'
    }

    stages {
         
         stage('build from a docker file'){
            steps {
                 script {
                     sh 'docker build -t ahmedgamil/docker-react -f Dockerfile.dev .'
                 }

            }

         }

            stage('run those tests'){
              steps {

                    script {

                        env.DOCKER_BUILDKIT = 1
                        sh 'docker run -e CI=true ahmedgamil/docker-react npm run test'
                    }

              }
            }

    }
}