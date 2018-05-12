@Library("pilipa-library") _

microServicePipeline(
    [
        'build': 'dotnetcoreMicroServiceRelease', 
        'imageName': 'pilipa/pluto', 
        'repoUrl': 'git@git.i-counting.cn:Agent/pluto.git',
        'credentialsId': 'jenkins at git.i-counting.cn', 
        'branch': 'dev', 
        'runner': 'MicroserviceCI/MicroserviceRunner',
        'serviceName': 'pilipa-pluto']
)
