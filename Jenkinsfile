pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/JitenPalaparthi/python-selenium-demo1'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'python3 -m venv venv'
                sh '. venv/bin/activate && pip install -r requirements.txt'
            }
        }

        stage('Run Selenium Tests') {
            steps {
                sh '. venv/bin/activate && python -m unittest tests/test_text_box.py -v'
            }
        }
    }
}