@Library("pilipa-library") _

microServicePipeline(build: 'nodeMicroServiceRelease', imageName: 'pilipa/organization', 
    repoUrl: 'git@git.i-counting.cn:pilipa/organization.git',
    credentialsId: 'jenkins at git.i-counting.cn', branch: 'dev',
    runner: 'MicroserviceCI/MicroserviceRunner',
    serviceName: 'pilipa-organization',
    logDriver: '--log-driver=json-file')