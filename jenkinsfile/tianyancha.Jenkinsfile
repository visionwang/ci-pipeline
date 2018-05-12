@Library("pilipa-library") _

microServicePipeline(build: 'javaMicroServiceRelease', imageName: 'pilipa/tianyancha', 
    repoUrl: 'git@git.i-counting.cn:pilipa/tianyancha.git',
    credentialsId: 'jenkins at git.i-counting.cn', branch: 'dev',
    runner: 'MicroserviceCI/MicroserviceRunner',
    serviceName: 'pilipa-tianyancha')
