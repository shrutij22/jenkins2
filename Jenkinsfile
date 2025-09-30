pipeline{
    agent any

    stages{
        stage('compile'){
            steps{
                sh 'javac Main.java'
            }
        }
        stage('Run'){
            steps{
                sh 'java Main'
            }
        }
        stage('Archive'){
            steps{
                archiveArtifacts artifacts: '*.class',fingerprint:true
            }
        }
    }

    post{
        failure{
            echo 'Build failed!'
        }
    }
}