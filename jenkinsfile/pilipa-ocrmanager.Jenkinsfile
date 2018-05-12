@Library("pilipa-library") _

microServicePipeline(
    [
        'build': 'dotnetcoreMicroServiceRelease', 
        'imageName':'pilipa/svt/ocrmanager', 
        'repoUrl': 'git@git.i-counting.cn:Agent/ocrManger.git',
        'credentialsId': 'jenkins at git.i-counting.cn', 
        'branch': 'dev', 
        'runner': 'MicroserviceCI/MicroserviceRunner',
        'serviceName': 'pilipa-svt-ocrmanager']
)
