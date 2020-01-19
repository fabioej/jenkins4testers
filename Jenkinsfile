pipeline {
    agent {
        docker {
            image "ruby:alpine"
        }
    }  
    stages {
        stage("Build"){
            steps {
                sh "chmod g+rx,o+rx /"
                sh "./build/alpine.sh"
                sh "bundle install"
            } 
        }
        stage("Tests") {
            steps {
               sh "bundle exec cucumber -p ci" 
            }
        }
       
    }
}