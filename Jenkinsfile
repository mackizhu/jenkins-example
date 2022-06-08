pipeline {
    agent any
    stages {
        stage('Example Build') {
            steps {
                echo 'Hello World'
            }
        }
        stage('Example Deploy') {
            when {
                branch 'master'
                environment name: 'DEPLOY_TO', value: 'master'
            }
            steps {
                echo 'Deploying ${DEPLOY_TO}'
            }
        }
    }
}
