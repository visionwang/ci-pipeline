@Library("pilipa-library") _

microServicePipeline(build: 'nodeMicroServiceRelease', imageName: 'pilipa/erp-backend', 
    repoUrl: 'git@git.i-counting.cn:ERP/erp-backend.git',
    credentialsId: 'jenkins at git.i-counting.cn', branch: 'dev',
    runner: 'MicroserviceCI/MicroserviceRunner',
    serviceName: 'pilipa-erp-backend',
    logDriver: '--log-driver=json-file')