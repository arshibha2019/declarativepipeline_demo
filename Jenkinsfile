pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/arshibha2019/declarativepipeline_demo.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Deploy to Tomcat') {
            steps {
                sh 'cp target/*.war /path/to/tomcat/webapps/'
            }
        }

        stage('Restart Tomcat') {
            steps {
                sh '/path/to/tomcat/bin/shutdown.sh || true'
                sh '/path/to/tomcat/bin/startup.sh'
            }
        }
    }
}
