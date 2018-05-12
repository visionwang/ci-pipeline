@Library("pilipa-library") _

microServicePipeline(build: 'nodeMicroServiceRelease', imageName: 'pilipa/cos-backend', 
    repoUrl: 'git@git.i-counting.cn:ERP/cos-backend.git',
    credentialsId: 'jenkins at git.i-counting.cn', branch: 'dev',
    runner: 'MicroserviceCI/MicroserviceRunner',
    serviceName: 'pilipa-cos-backend',
    logDriver: '--log-driver=json-file')