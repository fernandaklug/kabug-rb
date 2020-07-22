pipeline {
    agent {
        docker{
            image 'ruby'
        }
    }
    stages {
        stage('Buld') {
            steps {
                echo 'Building or Resolve Dependencies!'
                sh 'bundle install'
            }
        }
        stage ('Test') {
            steps {
                echo 'Runnin regression tests'
            }
        }
        stage ('UAT') {
            steps {
                echo 'Wait for User Acceptance'
                input(message: 'Go to production?', ok: 'Yes')
            }
        }
        stage ('Prod') {
            steps {
                echo 'WebApp is Ready :)'
            }
        }
    }
}