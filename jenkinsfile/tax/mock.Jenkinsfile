@Library("pilipa-library") _

microServicePipeline(build: 'javaMicroServiceRelease', imageName: 'pilipa/tax/mock',
		     repoUrl: 'git@git.i-counting.cn:tax/mock.git',
		     credentialsId: 'jenkins at git.i-counting.cn', branch: 'dev',
		     runner: 'MicroserviceCI/MicroserviceRunner',
		     serviceName: 'pilipa-mock')
