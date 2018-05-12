@Library("pilipa-library") _

microServicePipeline(
    [
        'build': 'dotnetcoreMicroServiceRelease', 
        'imageName':'pilipa/svt/schedulecenter', 
        'repoUrl': 'git@git.i-counting.cn:Agent/schedle.git',
        'credentialsId': 'jenkins at git.i-counting.cn', 
        'branch': 'dev', 
        'runner': 'MicroserviceCI/MicroserviceRunner',
        'serviceName': 'pilipa-svt-schedulecenter']
)
