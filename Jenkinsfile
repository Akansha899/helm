pipeline {
    agent any
    environment {
        IMAGE_REPOSITORY = 'cloudfreak.azurecr.io/cloudfreak/2020wa86188-dissertation'
        IMAGE_TAG = '1'
    }
    stages {
        stage('Deploy with Helm') {
            steps {           
                sh 'pwd'
                sh 'cp -R helm/* .'
                sh 'ls -ltr'
                sh 'pwd'
                sh "/usr/local/bin/helm upgrade --install 2020wa86188-app petclinic --set image.repository=${IMAGE_REPOSITORY} --set image.tag=${IMAGE_TAG}"
            }           
        }
    }
    post {
        success {
            echo 'Deployment successful.'
        }
        failure {
            echo 'Deployment failed.'
        }
    }
}
