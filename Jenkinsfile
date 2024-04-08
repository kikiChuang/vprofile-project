pipeline {
    
	agent any
    tools {
        maven "MAVEN3"
        jdk "OracleJDK8"
    }
    environment {
	SNAP_REPO = 'vprofile-snapshot'
        NEXUS_USER = 'admin'
        NEXUS_PASS = 'admin'
        NEXUS_VERSION = 'nexus3'
        NEXUS_PROTOCOL = 'http'
	NEXUSIP = '172.31.17.163'
        NEXUSPORT = '8081'
	RELEASE_REPO = 'vprofile-release'
	CENTRAL_REPO = 'vpro-maven-central'
        NEXUS_REPOSITORY = "vprofile-release"
	NEXUS_GRP_REPO    = 'vpro-maven-group'
        NEXUS_LOGIN = 'nexuslogin'
        ARTVERSION = "${env.BUILD_ID}"
    }

    stages{
        
        stage('BUILD'){
            steps {
                sh 'mvn -s settings.xml -DskipTests install'
            }
        }
    }
}
