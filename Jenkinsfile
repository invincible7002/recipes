pipeline {
    agent any

    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "JAVA_HOME = ${JAVA_HOME}"
                    echo "M2_HOME = ${M2_HOME}"
                                   '''
            }
        }

        stage ('Build') {
            steps {
                dir("/home/ec2-user/HelloWorld/recipes/recipes") {
                   
                sh 'mvn -Dmaven.test.failure.ignore=true -U clean install'
                }
               
            }
        }
       

        
  
        
        
        
        
 stage ('Deploy') {
            steps {
                dir("/home/ec2-user/HelloWorld/recipes/recipes") {
                sh 'mvn spring-boot:run'
                }
               
            }
}
       
    }
}
