pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/SupradeepanK/beginner-html-site-styled.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t html-site .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker rm -f html-container || true'
                sh 'docker run -d -p 80:80 --name html-container html-site'
            }
        }
    }
}
