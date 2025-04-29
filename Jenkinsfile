pipeline {
    agent any
    environment{
        APP_DIR = '/var/lib/jenkins/workspace/scripted_pipeline/Devops_JenkinsIntro'
        JAR_FILE = 'myapp-0.0.1-SNAPSHOT.jar'
    }

    stages{
        stage('Clean workspace'){
            steps{
                cleanWs()
            }
        }
        stage('Cloning the Git Repo') {
            steps {
               sh 'git clone https://github.com/Tejasvi02/Devops_JenkinsIntro.git'
            }
        }
        stage('Build appilcation') {
            steps {
               sh 'cd Devops_JenkinsIntro && mvn clean install'
            }
        }
        stage('Run Application'){
            steps{
                script{
                    sh 'cd $APP_DIR/target && java -jar $JAR_FILE'
                }
            }
        }
    }
}
