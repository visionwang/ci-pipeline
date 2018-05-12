@Library("pilipa-library") _

microServicePipeline(build: 'nodeMicroServiceRelease', imageName: 'pilipa/customer-api', 
    repoUrl: 'git@git.i-counting.cn:pilipa.cn/customer-api.git',
    credentialsId: 'jenkins at git.i-counting.cn', branch: 'dev',
    runner: 'MicroserviceCI/MicroserviceRunner',
    serviceName: 'pilipa-customer-backend')