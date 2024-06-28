pipeline {
    agent any
    
    environment {
        PATH = "/usr/bin/python3:/usr/local/bin:/usr/bin:/bin"
        // Assurez-vous que le chemin d'accès ci-dessus inclut le chemin où 'python3' et 'pip' sont installés
    }
    
    stages {
        stage('Build') {
            steps {
                script {
                    // Créer et activer un environnement virtuel
                    sh 'apt install python3.12-venv'

                    sh 'python3 -m venv pythenv'
                    sh '. pythenv/bin/activate && pip install --upgrade pip'
                    
                    // Installer pandas et autres dépendances
                    sh '. pythenv/bin/activate && pip install pandas'
                    
                    // Exécuter le script Python d'analyse de données
                    sh '. pythenv/bin/activate && python data_analysis.py'
                }
            }
        }
    }
}
