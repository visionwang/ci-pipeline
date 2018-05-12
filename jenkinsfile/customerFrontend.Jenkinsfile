@Library("pilipa-library") _

withCredentials([usernamePassword(credentialsId: 'oss-assets', passwordVariable: 'OSS_SECRET', usernameVariable: 'OSS_KEY')]){
    def buildEnv = "['NODE_ENV':'svt', 'REGION':'oss-cn-beijing-internal', 'ACCESS_KEY_ID':'${OSS_KEY}', \
            'ACCESS_KEY_SECRET':'${OSS_SECRET}', 'BUCKET':'pilipa-assets', 'FILE_DIR':'app/customerFrontend/', \
            'CSY_URL': 'https://x-id.i-counting.cn', 'UAA_SERVER_URL': 'https://x-id.i-counting.cn', 'CLIENT_ID': 'VIl880S3QSFNZ3Jj']"
    microServicePipeline(build: 'nodeMicroServiceRelease', imageName: 'pilipa/customer-frontend', 
        repoUrl: 'git@git.i-counting.cn:pilipa.cn/customer-frontend.git',
        credentialsId: 'jenkins at git.i-counting.cn', branch: "dev",
        buildEnvironments: buildEnv,
        runner: 'MicroserviceCI/MicroserviceRunner',
        serviceName: 'pilipa-customer-frontend')
}