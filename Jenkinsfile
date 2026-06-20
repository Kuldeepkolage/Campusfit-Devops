pipeline {
agent any

environment {
    DOCKER_IMAGE = "kuldeepkolage/campusfit"
    IMAGE_TAG = "${BUILD_NUMBER}"
}

stages {

    stage('Checkout') {
        steps {
            checkout scm
        }
    }

    stage('Build Docker Image') {
        steps {
            sh 'docker build -t $DOCKER_IMAGE:$IMAGE_TAG .'
        }
    }

    stage('Push Docker Image') {
        steps {
            withCredentials([
                usernamePassword(
                    credentialsId: 'dockerhub-credentials',
                    usernameVariable: 'DOCKER_USER',
                    passwordVariable: 'DOCKER_PASS'
                )
            ]) {
                sh '''
                    echo "$DOCKER_PASS" | docker login -u "$DOCKER_USER" --password-stdin
                    docker push $DOCKER_IMAGE:$IMAGE_TAG
                '''
            }
        }
    }

    stage('Deploy To Kubernetes') {
        steps {
            sh '''
                kubectl set image deployment/campusfit-app campusfit=$DOCKER_IMAGE:$IMAGE_TAG

                kubectl rollout status deployment/campusfit-app --timeout=120s
            '''
        }
    }

    stage('Verify Deployment') {
        steps {
            sh '''
                echo "===== Pods ====="
                kubectl get pods

                echo "===== Deployment ====="
                kubectl get deployment campusfit-app

                echo "===== Service ====="
                kubectl get svc
            '''
        }
    }
}

post {
    success {
        echo 'Deployment Successful 🚀'
    }

    failure {
        echo 'Deployment Failed ❌'
    }

    always {
        sh 'docker image prune -f || true'
    }
}

}
