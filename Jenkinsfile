node {
    printMessage("Démarrage du Pipeline")

    stage("Récupération du Code Source") {
      git "https://github.com/luyenge/ActivityA"
    }

    dir('Lesson5/ActivityA') {
        stage("Prérequis d'installation") {
            sh '. /home/maabik/.bash_profile  make install'
        }

        stage("Exécution de Tests") {
            sh '. /home/maabik/.bash_profile make jenkins_test'
        }

        stage("Deploiement") {
            if (env.BRANCH_NAME == "master") {
                printMessage("deploiement de la branche master encours")
            } else {
                printMessage("aucun deploiement specifié pour cette branche")
            }
        }
    }

    printMessage("Fin du Pipeline")
}

def printMessage(message) {
    echo "${message}"
}
