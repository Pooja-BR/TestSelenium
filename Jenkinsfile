pipeline {
    agent none
    
    stages {
        stage('gitclone') {
            agent any
            steps {
                sh "rm -rf TestSelenium"
                sh "git clone https://github.com/Pooja-BR/TestSelenium.git"
                sh "mvn clean -f mavenproject1"
            }
        }
        stage('compile') {
            agent any
            steps {
               sh "mvn compile -f TestSelenium"
            }
        }
        stage('Test') { 
            agent any
            steps {
                sh "mvn test -f TestSelenium" 
            }
        }
         stage('Deploy') { 
            agent any
            steps {
                sh "mvn package -f TestSelenium" 
            }
        }
    }
}

