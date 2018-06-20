node {
    stage('Example') {
        
    }

    stage('checkout-repo') {
        dir('express-demo') {
            git url: 'https://github.com/linwenjun/express-demo.git', branch: 'master'
        }
    }

    stage('checkout-answer') {
        dir('concourse-k8s-project') {
            git url: 'https://github.com/tws-training/concourse-k8s-project.git', branch: 'master'
        }
    }

    

    stage('standard') {
        currentBuild.result = 'SUCCESS'
        return
    }

    stage('standard-2') {
        sh 'ls express-demo'
        sh 'ls concourse-k8s-project'
    }

    def result = 1
    if (result == 1) {
        currentBuild.result = 'SUCCESS'
        echo "SUCCESS"
        return
    }
    
    stage('Example') {
        sh 'final stage'
    }
}
