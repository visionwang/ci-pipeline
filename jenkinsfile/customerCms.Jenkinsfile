@Library("pilipa-library") _

microServicePipeline(build: 'nodeMicroServiceRelease', imageName: 'pilipa/customer-cms', 
    repoUrl: 'git@git.i-counting.cn:pilipa.cn/customer-cms-final.git',
    credentialsId: 'jenkins at git.i-counting.cn', branch: "dev",
    runner: 'MicroserviceCI/MicroserviceRunner',
    serviceName: 'pilipa-customer-cms')