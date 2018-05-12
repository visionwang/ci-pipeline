@Library("pilipa-library") _

microServicePipeline(build: 'javaMicroServiceRelease', imageName: 'pilipa/magiceye/incoming', 
    repoUrl: 'git@git.i-counting.cn:note/backend/magiceye-incoming.git',
    credentialsId: 'jenkins at git.i-counting.cn', branch: 'dev',
    runner: 'MicroserviceCI/MicroserviceRunner',
    serviceName: 'pilipa-magiceye-incoming')
