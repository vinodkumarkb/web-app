@Library('vinod_shared_lib') _

pipeline {
    agent any
    
    tools{
        maven "MAVEN-3.9.4"
    }

    stages {
        
        
        stage('Clone') {
            steps {
               git branch: 'main', credentialsId: 'Github-password', url: 'https://github.com/vinodkumarkb/my-web-app.git'
            }
        }
        
        stage('Build') {
            steps {
              mavenBuild()
        }
        }
        
        stage('Code') {
            steps {
              sonarQube()
        }
        }
        
    }
}