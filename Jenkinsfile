pipeline {
    agent any
    tools{
        //Install the Maven version configured as "M3" and add it to the path.
        maven "M3"
    }

    stages {
        stage('Checkout') {
            steps {
                //get some code from a github repo
                
                git branch: 'main', url: 'https://github.com/aaliyah-rda/lbg-hello-world-maven.git'
            }
        }
        stage('Compile'){
            steps {
                //Run Maven on a Unix agent
                sh "mvn clean compile"
            }
        }
        stage('Test'){
            steps{
                sh "mvn test"
            }
        }
        stage('Package'){
            steps {
                sh "mvn -Dmaven.test.skip package"
            }
        }
    }
}
