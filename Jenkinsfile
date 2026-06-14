pipeline {
    agent any

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
    }
}
