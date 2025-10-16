pipeline {
    agent any
    environment {
        TOMCAT_HOME = "C:\Program Files\Apache Software Foundation\Tomcat 10.1"   // Path to your Tomcat installation
    }

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
                bat 'copy target\\*.war "%TOMCAT_HOME%\\webapps\\"'
            }
        }

        stage('Restart Tomcat') {
            steps {
                bat '"%TOMCAT_HOME%\\bin\\shutdown.bat" || echo Tomcat not running'
                bat '"%TOMCAT_HOME%\\bin\\startup.bat"'            }
        }
    }
}
