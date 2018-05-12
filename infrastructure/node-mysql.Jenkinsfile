@Library("pilipa-library") _

//properties([parameters([string(defaultValue: 'node-unittest', description: 'the name of image', name: 'IMAGE_NAME')])])
properties([parameters([string(defaultValue: '8', description: 'the name of tag', name: 'IMAGE_TAG')])])

dockerImage(
    repoUrl: 'git@git.i-counting.cn:ops/infrastructure.git',
    credentialsId: 'jenkins at git.i-counting.cn',
    branch: 'nodeunit',
    imageName: 'node-mysql',
    imageTag: "${params.IMAGE_TAG}",
    contextPath: 'docker/node/node-mysql/',
)
