@Library("pilipa-library") _

microServicePipeline(build: 'javaMicroServiceRelease', imageName: 'pilipa/authentication-server',
    repoUrl: 'git@git.i-counting.cn:pilipa/uaa/uaa.git',
    credentialsId: 'jenkins at git.i-counting.cn', branch: 'dev',
    runner: 'MicroserviceCI/MicroserviceRunner',
    serviceName: 'pilipa-authentication-server')
