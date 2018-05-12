@Library("pilipa-library") _

microServicePipeline(
    [
        'build': 'dotnetcoreMicroServiceRelease', 
        'imageName': 'pilipa/svt/accountnexus', 
        'repoUrl': 'git@git.i-counting.cn:accounting/core/nexus.git',
        'credentialsId': 'jenkins at git.i-counting.cn', 
        'branch': 'dev', 
        'runner': 'MicroserviceCI/MicroserviceRunner',
        'serviceName': 'pilipa-svt-accountnexus']
)
