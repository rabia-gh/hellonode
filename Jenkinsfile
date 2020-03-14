node {
    def app

    stage('Clone repository') {
        /* Let's make sure we have the repository cloned to our workspace */

        checkout scm
    }

    stage('Build image') {
        /* This builds the actual image; synonymous to
         * docker build on the command line */

       // app = docker.build("getintodevops/hellonode")
        sh '''docker build -f Dockerfile -t rabia97/hellonode . || true '''
    }
    stage('Push image') {
        withDockerRegistry([ credentialsId: "rabia97", url: "" ]) {
          sh 'docker push rabia97/hellonode:latest'
        }
    }
}
