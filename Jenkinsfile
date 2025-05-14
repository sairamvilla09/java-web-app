        }

        stage('Build') {
            steps {
                sh 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }

            post {
                always {
                    junit '**/target/surefire-reports/*.xml'
                }
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }

        // Optional - Docker stage (for later use)
        // stage('Docker Build') {
        //     steps {
        //         sh 'docker build -t java-web-app .'
        //     }
        // }
    }

    post {
        success {
            echo 'Build and Test Successful ✅'
        }
        failure {
            echo 'Build Failed ❌'
        }
    }
}

