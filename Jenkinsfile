pipeline {
    agent any
    environment {
      PATH = "/usr/bin/python3:/usr/bin/pip:$PATH"
    }
    stages {
        stage('Build') {
            steps {
                script {
                    // Choisissez la commande en fonction de votre script
                    sh python3 -m venv pythenv
                    sh source myenv/bin/activate
                    sh 'pip install pandas' // Installer les dépendances
                    sh 'python data_analysis.py' // Exécuter le script Python
                }
            }
        }
    }
}
