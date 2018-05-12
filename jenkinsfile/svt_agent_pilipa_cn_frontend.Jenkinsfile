@Library("pilipa-library") _
def buildEnv = ""
microServicePipeline(build: 'nodeMicroServiceRelease', imageName: 'pilipa/agent-backbone-dev',
    repoUrl: 'git@git.i-counting.cn:Agent/agent_backbone.git',
    credentialsId: 'jenkins at git.i-counting.cn', branch: "dev",
    buildEnvironments: buildEnv,
    runner: 'MicroserviceCI/MicroserviceRunner',
    serviceName: 'pilipa-agent-pilipa-cn-frontend-development',
    context: './deploy')