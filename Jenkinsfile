pipeline {
    agent any
    tools{
        maven 'maven 3.8'
    }
    
     stages {
        stage('checkout') {
            steps {
                echo 'git cloning'
                git branch: 'main', url: 'https://github.com/Raki-10/Pipeline.git'
            }
        }
        stage('build') {
            steps {
                echo 'building maven'
                sh 'mvn clean install'
            }
        }
        stage('test') {
            steps {
                echo 'testing'
                sh "mvn test"
            }
        }
        
    }
    post {
        always{
            junit '**/target/surefire-reports/TEST-com.rakesh143.rr85.AppTest.xml'
        }
    }
}

