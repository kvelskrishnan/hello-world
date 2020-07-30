pipeline {
    agent {
        docker {
            image 'maven:3-alpine'
            args '-v $HOME/.m2:/root/.m2'
        }
    }
    stages {
        //stage('checkout') {
            //steps {
               // checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'd17e11c4-36b2-4a3c-8e1b-0f4c172804ca', url: 'https://kathir_s@bitbucket.org/cdeonedevops/devops_poc.git']]])
            //}
        //}
        stage('Build') {
            steps {
                sh 'mvn -B clean install'
            }
        }
        //stage('Unit Test') {
            
           // steps {

             //   sh 'mvn test'
            //}
            //post {
              //  always {
                //    junit 'target/surefire-reports/*.xml'
                //}
           // }
        //}
       // stage('Code Quality - Analysis') {
            
         //   steps {

            //    sh "mvn sonar:sonar -Dsonar.host.url=http://cdedevops-lab.eastus.cloudapp.azure.com/:9000 -Dsonar.login=527594b9d7617417d8b08075f9167f2b95735bd0"
           // }
        //}
        stage('docker build') {
            steps {
                sh "docker build -t $JOB_BASE_NAME:$BUILD_NUMBER ."
            }
        }
    }
}
