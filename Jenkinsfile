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
                sh 'cp target/*.war C:\Program Files\Apache Software Foundation\Tomcat 10.1\webapps'
            }
        }

        stage('Restart Tomcat') {
            steps {
                sh 'C:\Program Files\Apache Software Foundation\Tomcat 10.1\bin\shutdown || true'
                sh '/path/to/tomcat/bin/startup'            }
        }
    }
}
