@Library("pipeline-library") _

properties([parameters([string(defaultValue: 'yuuyoo/openjdk', description: 'the name of image', name: 'IMAGE_NAME')])])
properties([parameters([string(defaultValue: '1.8', description: 'the name of tag', name: 'IMAGE_TAG')])])

dockerImage(
    repoUrl: 'git@github.com:xiaoyingxi/infrastructure.git',
    credentialsId: '9daced0c-e897-4c39-86d7-c6834e490ab4',
    branch: 'master',
    imageName: "${params.IMAGE_NAME}",
    imageTag: "${params.IMAGE_TAG}",
    contextPath: 'docker/java/',
)
