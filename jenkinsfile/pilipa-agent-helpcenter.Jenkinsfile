@Library("pilipa-library") _
def buildEnv = ""
microServicePipeline(build: 'nodeMicroServiceRelease', imageName: 'pilipa/agent/helpcenter',
    repoUrl: 'git@git.i-counting.cn:Agent/infocenter.git',
    credentialsId: 'jenkins at git.i-counting.cn', branch: "dev",
    buildEnvironments: buildEnv,
    runner: 'MicroserviceCI/MicroserviceRunner',
    serviceName: 'pilipa-agent-helpcenter')