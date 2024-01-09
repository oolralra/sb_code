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
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
