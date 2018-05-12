@Library("pilipa-library") _

microServicePipeline(
    [
        'build': 'dotnetcoreMicroServiceRelease', 
        'imageName': 'pilipa/national-tax-jiangsu', 
        'repoUrl': 'git@git.i-counting.cn:tax/jiangsu-national-tax.git',
        'credentialsId': 'jenkins at git.i-counting.cn', 
        'branch': 'dev1', 
        'runner': 'MicroserviceCI/MicroserviceRunner',
        'serviceName': 'pilipa-national-tax-jiangsu']
)
