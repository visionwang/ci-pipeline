@Library("pilipa-library") _

microServicePipeline(build: 'javaMicroServiceRelease', imageName: 'pilipa/accounting/morgan',
    repoUrl: 'git@git.i-counting.cn:accounting/process/morgan.git',
    credentialsId: 'jenkins at git.i-counting.cn', 
    branch: 'dev',
    runner: 'MicroserviceCI/MicroserviceRunner',
    serviceName: 'pilipa-accounting-morgan')
