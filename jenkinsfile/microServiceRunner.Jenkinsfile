@Library("pipeline-library") _

pipeline {
    agent { label 'build-server' }
    options {
        buildDiscarder(logRotator(numToKeepStr: '100', daysToKeepStr: '30'))
        timeout(time: 10, unit: 'MINUTES')
        timestamps()
    }
    parameters {
        choice(name: 'SERVICE', description: 'the service to be started', 
            choices: 'yuuyoo-demo\n\
                      pilipa-organization\
                      ')

        choice(name: 'LOGDRIVER', description: 'the container log driver', 
            choices: '--log-driver=fluentd --log-opt=fluentd-address=fluentd.i-counting.cn:24224 --log-opt=tag=pilipa.{{.Name}}.{{.ImageName}}\n\
                      --log-driver=json-file\
                      ')

        string(name: 'VERSION', defaultValue: 'latest', description: 'the version of image to be used')
        string(name: 'ENVIRONMENTS', defaultValue: '',description: '(Optional)the environments to be used to run service')
        string(name: 'REPLICAS',defaultValue: '',description: '(Optional)the replicas of service')
        string(name: 'MEMORY', defaultValue: '', description: '(Optional)the memory of container')
        string(name: 'NETWORK', defaultValue: '', description: '(Optional)the network of container')
        string(name: 'PUBLISH', defaultValue: '', description: '(Optional)the publish portts of container')
    }
    stages {
        stage('Starting micro service') {

            steps {
                script { 
                    def DEFAULT_JAVA_OPTS = "-server -XX:+HeapDumpOnOutOfMemoryError -XX:HeapDumpPath=/var/yuuyoo/ \
                        -Duser.timezone=Asia/Shanghai -Dspring.profiles.active=svt -Deureka.instance.hostname=\${HOST}"
                    def ENVIRONMENTS = "['JAVA_OPTIONS':'${DEFAULT_JAVA_OPTS}']"
                    def PARAMMAP = [
                                "SERVICE_NAME":params.SERVICE.trim(),
                                "IMAGE_NAME":"yuuyoo/demo",
                                "VERSION":"latest",
                                "ENVIRONMENTS":ENVIRONMENTS,
                                "REPLICAS":"1",
                                "MEMORY":"512M",
                                "NETWORK":"['yuuyoo-network']"
                    ]
                    switch (PARAMMAP["SERVICE_NAME"]){
                        case "yuuyoo-demo":
                            PARAMMAP["IMAGE_NAME"] = "yuuyoo/demo"
                            break
                        case "pilipa-configserver":
                            PARAMMAP["IMAGE_NAME"] = "pilipa/configserver"
                            withCredentials([usernamePassword(credentialsId: 'svt_rabbit_password', passwordVariable: 'RABBIT_PASSWORD', usernameVariable: 'RABBIT_PASSWORD_KEY')]) {
                                PARAMMAP["ENVIRONMENTS"] = "['JAVA_OPTIONS':'${DEFAULT_JAVA_OPTS} \
                                     -Djava.security.egd=file:/dev/./urandom -Dspring.rabbitmq.password=${RABBIT_PASSWORD}']" 
                            }
                            break
                        case "pilipa-organization":
                            PARAMMAP["IMAGE_NAME"] = "pilipa/organization"
                            PARAMMAP["ENVIRONMENTS"] = "['NODE_ENV':'svt']"
                            break   
                        default:
                            throw new Exception("Service name '${params.SERVICE}' is unknown!")
                    }

                    def SERVICE_NAME = PARAMMAP["SERVICE_NAME"]
                    def IMAGE_NAME = PARAMMAP["IMAGE_NAME"]
                    def VERSION = params.VERSION!=''?params.VERSION:PARAMMAP["VERSION"]
                    def ENVIRONMENTSUSED = params.ENVIRONMENTS!=''?params.ENVIRONMENTS:PARAMMAP["ENVIRONMENTS"]
                    def REPLICAS = params.REPLICAS!=''?params.REPLICAS:PARAMMAP["REPLICAS"]
                    def MEMORY = params.MEMORY!=''?params.MEMORY:PARAMMAP["MEMORY"]
                    def NETWORK = params.NETWORK!=''?params.NETWORK:PARAMMAP["NETWORK"]
                    def PUBLISH = params.PUBLISH!=''?params.PUBLISH:PARAMMAP["PUBLISH"]
                    def LOGDRIVER = params.LOGDRIVER

                    microServiceStart{
                        logDriver = LOGDRIVER
                        dockerServiceName = SERVICE_NAME
                        imageName = IMAGE_NAME
                        tagId = VERSION
                        registry = "registry.yuuyoo.com"
                        environment = ENVIRONMENTSUSED
                	    replicas = REPLICAS
                	    limitMemory = MEMORY
                        network = NETWORK
                        publish = PUBLISH
                    } 
                }
            }
        }
    }
}
