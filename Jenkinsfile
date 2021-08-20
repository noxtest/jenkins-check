node {
    checkout scm

    def customImage = docker.build("Dockerfile-debian:${env.BUILD_ID}")

    customImage.inside {
        sh './tests/linux-run.sh'
    }
}
