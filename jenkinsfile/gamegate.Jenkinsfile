@Library("pipeline-library") _

def buildEnv = "['FILTER_CLIENT_ID':'AS6vl1WwLGnTY0id']"
microServicePipeline(build: 'nodeMicroServiceRelease', 
    imageName: 'yuuyoo/gamegate', 
    repoUrl: 'git@github.com:xiaoyingxi/node-gateway.git',
    credentialsId: '9daced0c-e897-4c39-86d7-c6834e490ab4', 
    branch: 'master',
    runner: 'microServiceRunner',
    buildEnvironments: buildEnv,
    serviceName: 'yuuyoo-gamegate')
