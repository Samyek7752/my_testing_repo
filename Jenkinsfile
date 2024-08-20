
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                dir('/root/git/project/') {
                    sh 'mvn clean install'
                }
            }
        }

        stage('Copy WAR to Tomcat') {
            steps {
                sh 'cp -r /root/git/project/target/*.war /root/tom/apache-tomcat-9.0.93/webapps/'
            }
        }
    }

    post {
        always {
            echo 'WAR file copied to /webapps successfully.'
        }
    }
}
