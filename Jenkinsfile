pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    docker.image('node:18-alpine').inside {
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
