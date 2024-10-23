{
 stages {
        stage('clone repo') {
            steps {
                echo "Clone the Git repository"
                git clone 'https://github.com/jaheda06/maven-web-app.git'
            }
        }

        stage('Build') {
            steps {
                echo "build the maven project"
                bat 'mvn clean package'
            }
        }

        stage('Deploy') {
            steps {
                echo "connected to ec2-instance and ready to deploy"
                bat '''
                scp -i F:/New folder/jaheda.pem target/01-maven-web-app.war ec2-user@3.108.66.246:/home/ec2-user/
                '''
            }
        }
    }
}
