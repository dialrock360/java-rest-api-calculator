pipeline {
    agent any

    stages {
        
       stage('Clean'){
            steps{
                cleanWs()
            }
        } 
        
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
                bat('mvnw clean test')
                   }
            }
        } 
        stage('Test Integration'){
            steps{
                bat 'mvnw sonar:sonar'
            }
        }
        
     
    
          stage('Test Compilation'){
            steps{
                bat 'mvnw compile'
            }
        }
        
    
          stage('Test deploiment'){
            steps{
                bat 'mvnw deploy'
            }
        }
        
    }
    

}
