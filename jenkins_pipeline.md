
pipeline {
    agent any

    stages {
        stage('Git Clone and Clean') {
            steps {
                sh 'rm -rf MavenJava'
                sh 'git clone https://github.com/psabc550-eng/MavenJava.git MavenJava'
                sh 'mvn -f MavenJava/pom.xml clean'
            }
        }

        stage('Install') {
            steps {
                sh 'mvn -f MavenJava/pom.xml install'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn -f MavenJava/pom.xml test'
            }
        }

        stage('Package') {
            steps {
                sh 'mvn -f MavenJava/pom.xml package'
            }
        }
    }
}
