pipeline{
    agent any

    stages{
        stage('compile'){
            steps{
                sh 'javac src/Main.java'
            }
        }
        stage('Run'){
            steps{
                sh 'java -cp src Main'
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