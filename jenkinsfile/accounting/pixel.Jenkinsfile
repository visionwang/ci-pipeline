@Library("pilipa-library") _

microServicePipeline(build: 'javaMicroServiceRelease', imageName: 'pilipa/accounting/pixel',
    repoUrl: 'git@git.i-counting.cn:accounting/core/pixel.git',
    credentialsId: 'jenkins at git.i-counting.cn',
    branch: 'dev',
    runner: 'MicroserviceCI/MicroserviceRunner',
    serviceName: 'pilipa-accounting-pixel')
