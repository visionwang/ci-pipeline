@Library("pilipa-library") _

def buildEnv = "['FILTER_CLIENT_ID':'AS6vl1WwLGnTY0id']"
microServicePipeline(build: 'nodeMicroServiceRelease', imageName: 'pilipa/authentication-server/frontend', 
    repoUrl: 'git@git.i-counting.cn:pilipa/uaa/uaa-frontend.git',
    credentialsId: 'jenkins at git.i-counting.cn', branch: 'dev',
    runner: 'MicroserviceCI/MicroserviceRunner',
    buildEnvironments: buildEnv,
    serviceName: 'pilipa-authentication-server-frontend')
