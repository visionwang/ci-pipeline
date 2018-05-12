@Library("pilipa-library") _

properties([parameters([string(defaultValue: 'maintenance', description: 'the remote branch to be deploy', name: 'branch')])])

microServicePipeline(build: 'nodeMicroServiceRelease', imageName: 'pilipa/customer-api-maintenance', 
    repoUrl: 'git@git.i-counting.cn:pilipa.cn/customer-api.git',
    credentialsId: 'jenkins at git.i-counting.cn', branch: "${params.branch}",
    runner: 'MicroserviceCI/MicroserviceRunner',
    serviceName: 'pilipa-maintenance-customer-backend')