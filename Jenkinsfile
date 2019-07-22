pipeline {
    agent any

    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    
                    echo "JAVA_HOME = ${JAVA_HOME}"
                    echo "M2_HOME = ${M2_HOME}"
                                   '''
            }
        }

        stage ('Build') {
            steps {
                dir("/home/durgeshgaur/HelloWorld/recipes") {
                export JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64    
                sh 'mvn -Dmaven.test.failure.ignore=true -U clean install'
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
