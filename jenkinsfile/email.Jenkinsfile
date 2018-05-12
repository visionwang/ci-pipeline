@Library("pilipa-library") _

microServicePipeline(build: 'javaMicroServiceRelease', imageName: 'pilipa/email', 
    repoUrl: 'git@git.i-counting.cn:pilipa/email.git',
    credentialsId: 'jenkins at git.i-counting.cn', branch: 'dev',
    runner: 'MicroserviceCI/MicroserviceRunner',
    serviceName: 'pilipa-email')
