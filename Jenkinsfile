node {

    checkout scm

    docker.withRegistry('https://registry.hub.docker.com', 'rabia97') {

        def customImage = docker.build("rabia97/hellonode")

        /* Push the container to the custom Registry */
        customImage.push()
    }
}
