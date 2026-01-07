node {
    stage("Checkout"){
        checkout([$class: 'GitSCM',
                  branches: [[name: '*/hetzner']],
                  userRemoteConfigs: [[credentialsId: 'git',
                  url: 'https://github.com/IslamHamada/petshop_deployment.git']]])
    }
    stage("Deploy Pods"){
        withCredentials([file(credentialsId: 'k3s-kubeconfig', variable: 'KUBECONFIG_FILE')]){
            sh("kubectl --kubeconfig=${KUBECONFIG_FILE} apply -f k8s/config-maps.yaml")
            sh("kubectl --kubeconfig=${KUBECONFIG_FILE} apply -f k8s/mysql-deployment.yaml")
            sh("kubectl --kubeconfig=${KUBECONFIG_FILE} apply -f k8s/zipkin-deployment.yaml")
        }
    }
}