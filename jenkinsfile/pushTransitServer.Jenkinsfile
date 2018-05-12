@Library("pilipa-library") _

microServicePipeline(build: 'nodeMicroServiceRelease', imageName: 'pilipa/push-transit-server', 
    repoUrl: 'git@git.i-counting.cn:pilipa/push-transit-server.git',
    credentialsId: 'jenkins at git.i-counting.cn', branch: 'dev',
    runner: 'MicroserviceCI/MicroserviceRunner',
    serviceName: 'pilipa-push-transit-server')