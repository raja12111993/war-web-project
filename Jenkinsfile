pipeline {
    agent any

    environment {
        // Optionally define Maven settings or Java version
        M2        = '/opt/maven/bin'
        M2_HOME   = '/opt/maven'
        PATH      = "${env.M2}:${env.PATH}"
    }

    stages {
        stage('Checkout from GitHub') {
            steps {
                echo 'Cloning repository...'
                git url: 'https://github.com/raja12111993/war-web-project.git', branch: 'master'
            }
        }

        stage('Build with Maven') {
            steps {
                echo 'Building project with Maven...'
                sh 'mvn clean install'
            }
        }
    }

    post {
        success {
            echo 'Build completed successfully!'
        }
        failure {
            echo 'Build failed. Check logs.'
        }
    }
}
