@Library("pilipa-library") _

microServicePipeline(build: 'javaMicroServiceRelease', imageName: 'note/backend/vat',
    repoUrl: 'git@git.i-counting.cn:note/backend/vat.git',
    credentialsId: 'jenkins at git.i-counting.cn', branch: 'dev',
    runner: 'MicroserviceCI/MicroserviceRunner',
    serviceName: 'pilipa-vat')
