@Library("pilipa-library") _

microServicePipeline(build: 'nodeMicroServiceRelease', imageName: 'pilipa/sms-yuntongxun-server', 
    repoUrl: 'git@git.i-counting.cn:pilipa/sms-yuntongxun-server.git',
    credentialsId: 'jenkins at git.i-counting.cn', branch: 'dev',
    runner: 'MicroserviceCI/MicroserviceRunner',
    serviceName: 'pilipa-sms-ytx')