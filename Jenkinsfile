pipeline {
//     environment {
//         JAVA_TOOL_OPTIONS = "-Duser.home=/root/.m2"
//     }
    agent {
        docker {
            image "maven:3.8.1-adoptopenjdk-8"
            label "master"
            //args "-v /tmp/maven:/var/maven/.m2 -e MAVEN_CONFIG=/var/maven/.m2"
            args '-v /root/.m2:/root/.m2'
        }
    }

    stages {
        stage("Build") {
            steps {
                sh "mvn -version"
                sh "mvn clean install"
            }
        }
    }

    post {
        always {
            cleanWs()
        }
    }
}
