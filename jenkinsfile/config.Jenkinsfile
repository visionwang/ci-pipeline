@Library("pipeline-library") _

microServicePipeline(
    build: 'javaMicroServiceRelease', 
    imageName: 'yuuyoo/config',
    repoUrl: 'git@github.com:xiaoyingxi/spring-boot-config.git',
    credentialsId: '9daced0c-e897-4c39-86d7-c6834e490ab4', 
    branch: 'master',
    runner: 'MicroserviceRunner',
    logDriver: '--log-driver=json-file',
    serviceName: 'yuuyoo-config')
