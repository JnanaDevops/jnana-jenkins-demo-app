pipeline {
    agent {
        label 'build-node'
    }

   // tools {
        // Install the maven version configured as "M3" and add it to the path.
        //maven "M398"
    //}

    stages {
        stage('Echo Version'){
            steps {
                sh 'echo Print Maven Version'
                sh 'mvn -version'
            }
        }
        stage('Create-Workspace'){
            steps {
                echo 'creating workspace'
                //sh 'ls -lrth /var/lib/jenkins'
            }
        }
        stage('clone-repo'){
            steps {
                git branch: 'main',
                    url: 'https://github.com/JnanaDevops/jnana-jenkins-demo-app.git'
            }
        }
        stage('Build'){
            steps {
                // Get some code from a Gitea repo
                // git branch: 'main', url: 'https:.......'
                // Run Maven Package CMD
                // In Maven, the -D option stands for "Define a system property".
                sh "mvn clean package -DskipTests=true"
            }
        }
        stage('Unit Test'){
            steps {
                sh "mvn test"
            }
        }
        stage('Docker build') {
            steps {
                sh 'docker build -t jnana-java-webapp:latest .'
            }
        }
    }
}
