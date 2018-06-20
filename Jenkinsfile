pipeline {
    agent any

    environment {
        NameSpace='linwenjun'
    }

    stages {

        stage('checkout-repo') {
            steps {
                dir('express-demo') {
                    git url: 'https://github.com/linwenjun/express-demo.git', branch: 'master'
                }
            }
        }

        stage('checkout-answer') {
            steps {
                dir('concourse-k8s-project') {
                    git url: 'https://github.com/tws-training/concourse-k8s-project.git', branch: 'master'
                }
            }
        }

        stage('standard') {
            steps {
                if( $VALUE1 == $VALUE2 ) {
                    currentBuild.result = 'SUCCESS'
                    return
                }
            }
        }

        stage('standard-2') {
            steps {
                sh 'ls express-demo'
                sh 'ls concourse-k8s-project'
            }
        }
    }
}