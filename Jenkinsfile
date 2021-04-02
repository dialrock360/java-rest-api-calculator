pipeline {
    agent any

    stages {
        
       stage('Clean'){
            steps{
                cleanWs()
            }
        } bat
        
        stage('Source') {
            steps{
                git(
                        url: 'https://github.com/libane97/rest-api-calculator-java.git',
                        branch: 'main'
                    ) 
            }
        }
 
        stage('Test Unitaire'){
            
            steps{
                 script{
                sh('mvnw clean test')
                   }
            }
        } 
        stage('Test Integration'){
            steps{
                sh 'mvnw sonar:sonar'
            }
        }
        
     
    
          stage('Test Compilation'){
            steps{
                sh 'mvnw compile'
            }
        }
        
    
          stage('Test deploiment'){
            steps{
                sh 'mvnw deploy'
            }
        }
        
    }
    

}
