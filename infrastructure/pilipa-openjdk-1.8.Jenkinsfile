@Library("pilipa-library") _

properties([parameters([string(defaultValue: 'pilipa/openjdk', description: 'the name of image', name: 'IMAGE_NAME')])])
properties([parameters([string(defaultValue: '1.8', description: 'the name of tag', name: 'IMAGE_TAG')])])

dockerImage(
    repoUrl: 'git@git.i-counting.cn:ops/infrastructure.git',
    credentialsId: 'jenkins at git.i-counting.cn',
    branch: 'master',
    imageName: "${params.IMAGE_NAME}",
    imageTag: "${params.IMAGE_TAG}",
    contextPath: 'docker/java/',
)
