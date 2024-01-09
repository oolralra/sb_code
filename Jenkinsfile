pipeline {
    agent any
    
    tools {
        maven 'my_maven'
    }
    environment {
        GITNAME = 'Brilly-Bohyun'
        GITEMAIL = 'choibohyun81@gmail.com'
        GITWEBADD = 'https://github.com/Brilly-Bohyun/sb_code.git'
        GITSSHADD = 'git@github.com:Brilly-Bohyun/sb_code.git'
        GITCREDENTIAL = 'git_cre'
    }
    
    stages {
        stage('Checkout Github') {
            steps {
                 checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [],
                 userRemoteConfigs: [[credentialsId: GITCREDENTIAL, url: GITWEBADD]]])
            }
        
            post {
        
                failure {
                    echo 'Repository clone failure'
                }
                success {
                    echo 'Repository clone success'
                }
            }
        }
        
        
        stage('code build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('image build') {
            steps {
                sh "docker build -t bohyunchoi/spring:1.0 ."
            }
        }
    }
}
