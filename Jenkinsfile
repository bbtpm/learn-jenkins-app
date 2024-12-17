/*pipeline {
    agent any
 
    stages {
        stage('with Docker') {
            agent{
                docker{
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    echo "with docker"
                    npm --version
                    touch "with-container.txt"
                '''
            }
        }
        stage('without Docker') {
            steps {
                sh '''
                    echo "without docker"
                    touch "without-container.txt"
                '''
            }
        }
       
    }
}
*/

pipeline {
    agent any
 
    stages {
        stage('Build') {
            agent{
                docker{
                    image 'node:18-alpine'
                    reuseNode true
                }
            }
            steps {
                sh '''
                  ls -la
                  node --version
                  npm --version
                  npm ci
                  npm run build
                  ls -la
                ''' //la ดูทุกไฟล์ ci
            }
        }
    }
}