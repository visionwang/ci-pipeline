@Library("pilipa-library") _

microServicePipeline(
    [
        'build': 'dotnetcoreMicroServiceRelease', 
        'imageName': 'pilipa/svt/autocalculate', 
        'repoUrl': 'git@git.i-counting.cn:accounting/core/R._Daneel_Olivaw.git',
        'credentialsId': 'jenkins at git.i-counting.cn', 
        'branch': 'dev', 
        'runner': 'MicroserviceCI/MicroserviceRunner',
        'serviceName': 'pilipa-svt-autocalculate']
)
