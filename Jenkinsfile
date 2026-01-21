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
            steps{
                //supprimer le fichier repo
                sh 'rm -rf repo'
            }
            steps{
                //cloner l'adresse git du projet 
                
                sh "git clone https://github.com/Johannap19/PlaywrightJenkins.git repo"
            }
                steps{
                //check version de node et playwright
                sh "echo 'node --version'"
                sh "echo 'np playwright --version'"
            }
             steps{
                //acceder au projet repo avec la commannde dir 
                dir('repo')
                sh "npm install"
                sh "npx playwright test --project=chromium"
            }

        }
    }
}