pipeline{
    agent any
    stages{
        stage('Checkout'){
            steps{
                git branch:'main', url:"https://github.com/tanay25/deepak.git"
                echo "Step 1 : Source Code is ready"
            }
        }
        stage('Check Python'){
            steps{
                sh 'python3 --version'
            }
        }
        stage("Install Dependenc"){
            steps{
                sh '''
                    python3 -m venv .venv
                    .venv/bin/python -m pip install --upgrade pip
                    .venv/bin/python -m pip install -r requirements.txt 
                '''
            }
        }
        stage('Run Tests'){
            steps{
                sh '.venv/bin/python -m pytest -v'
            }
        }
        stage('Run Application'){
            steps{
                sh '.venv/bin/python app.py'
            }
        }
    }
    
}