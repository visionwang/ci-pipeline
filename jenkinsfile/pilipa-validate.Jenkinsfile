@Library("pilipa-library") _

microServicePipeline(
    [
        'build': 'dotnetcoreMicroServiceRelease', 
        'imageName':'pilipa/svt/validate', 
        'repoUrl': 'git@git.i-counting.cn:pilipa/validate.git',
        'credentialsId': 'jenkins at git.i-counting.cn', 
        'branch': 'dev', 
        'runner': 'MicroserviceCI/MicroserviceRunner',
        'serviceName': 'pilipa-svt-validate']
)
