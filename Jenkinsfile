node {
    stage('Clone repository') {
        git credentialsId: 'github-access-token', url: 'https://github.com/ktemple77/jenkins-mydiary-msa.git'
    }

    stage('Build image') {
       dockerImage = docker.build("ktemple77/mydiary-front:2.0")
    }

    stage('Push image') {
        withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
        dockerImage.push()
        }
    }
}
