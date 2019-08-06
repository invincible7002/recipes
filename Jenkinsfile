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
                dir("/home/durgeshgaur/HelloWorld/recipes") {
                sh 'export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64'    
                sh 'mvn -Dmaven.test.failure.ignore=true -U clean install'
                }
               
            }
        }
       
         stage ('UnitTest') {
            steps {
                dir("/home/durgeshgaur/HelloWorld/recipes") {
               sh 'mvn sonar:sonar   -Dsonar.projectKey=test   -Dsonar.host.url=http://localhost:9000   -Dsonar.login=2c3b0a7284cbe38b6e92924b0bbbce7d83b111d8'
                }
            }
         
}
        
        
        
 stage ('Deploy') {
            steps {
                dir("/home/durgeshgaur/HelloWorld/recipes") {
                sh 'mvn spring-boot:run'
                }
               
            }
}
       
    }
}
