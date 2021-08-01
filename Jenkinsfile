pipeline{
    agent{label 'master'}
    tools{maven 'M3'}
    stages{
        stage('Ckeckout'){
            steps{
                git branch: 'main', url: 'https://github.com/init-esh/SpringPetClinic.git'
                
            }
        }
        stage('Build'){
            steps{
                sh 'mvn compile'
            }
        }
        stage('Test'){
            steps{
                sh 'mvn test'
            }
        }
        stage('Package'){
            steps{
                sh 'mvn package'
            }
        }
        stage('Depoly'){
            steps{
                sh 'java -jar /var/lib/jenkins/workspace/PetClinicDecPipeline/target/*.jar'
            }
        }
    }
}
