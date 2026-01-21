pipeline{
    //installer l'environnement 
    //nodesjs, playwright
    agent{
         docker {
            image 'playwright/chromium:playwright-1.56.1'
            args '--user=root --entrypoint=""'
        } 
    }
    stages{
            stage("démarrage de configuration projet"){
                steps {
                    sh 'node --version'
                    sh 'npm --version'
                    sh 'npm install'
                    sh 'npx playwright install'
                    sh 'npx playwright test'

                }
              
        }
    }
}