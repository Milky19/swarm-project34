pipeline {
    agent any

    stages {
        stage('clone-project') {
            steps {
                git 'https://github.com/Milky19/swarm-project34.git'
            }
        }
        stage('Build-image'){
            steps{
                sh 'docker build -t $image .'
            }
        }
        stage('tagging-images'){
            steps{
                sh 'docker tag $image $repo'
            }
        }
        stage('Push-images-Registery'){
            steps{
                sh 'docker login -u hanvitha -p $password'
                sh 'docker push $repo'
            }
        }
    }
}

