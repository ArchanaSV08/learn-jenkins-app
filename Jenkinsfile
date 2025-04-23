pipeline {
    agent none

    stages {
        stage('Build') {
            agent {
                label 'docker' // This assumes your Jenkins node can run Docker
            }
            environment {
                DOCKER_IMAGE = 'node:18-alpine'
            }
            steps {
                script {
                    docker.image(env.DOCKER_IMAGE).inside {
                        sh '''
                            ls -la
                            node --version
                            npm -v
                            npm ci
                            npm run build
                            ls -la
                        '''
                    }
                }
            }
        }
    }
}
