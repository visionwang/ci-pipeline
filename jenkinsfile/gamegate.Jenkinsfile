@Library("pilipa-library") _

def buildEnv = "['FILTER_CLIENT_ID':'AS6vl1WwLGnTY0id']"
microServicePipeline(build: 'nodeMicroServiceRelease', imageName: 'yuuyoo/gamegate', 
    repoUrl: 'git@github.com:xiaoyingxi/node-gateway.git',
    credentialsId: 'jenkins at git.i-counting.cn', branch: 'dev',
    runner: 'MicroserviceCI/MicroserviceRunner',
    buildEnvironments: buildEnv,
    serviceName: 'yuuyoo-gamegate')
