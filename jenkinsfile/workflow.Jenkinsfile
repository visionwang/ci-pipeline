@Library("pilipa-library") _

microServicePipeline(build: 'javaMicroServiceRelease', imageName: 'pilipa/workflow',
    repoUrl: 'git@git.i-counting.cn:tax/workflow.git',
    credentialsId: 'jenkins at git.i-counting.cn', branch: 'dev',
    runner: 'MicroserviceCI/MicroserviceRunner',
    serviceName: 'pilipa-workflow')
