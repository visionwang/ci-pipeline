@Library("pipeline-library") _

microServicePipeline(
    build: 'nodeMicroServiceRelease', 
    imageName: 'yuuyoo/demo',
    repoUrl: 'git@github.com:xiaoyingxi/node-demo.git',
    credentialsId: '9daced0c-e897-4c39-86d7-c6834e490ab4', 
    branch: 'master',
    runner: 'microServiceRunner',
    logDriver: '--log-driver=json-file',
    serviceName: 'yuuyoo-demo')
