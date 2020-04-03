node {
    printMessage("Démarrage du Pipeline")

    stage("Récupération du Code Source") {
      git "https://github.com/luyenge/Beginning-Jenkins/tree/master/Lesson5/ActivityA"
    }

    dir('Lesson5/ActivityA') {
        stage("Prérequis d'installation") {
            sh 'make install'
        }

        stage("Exécution de Tests") {
            sh 'make jenkins_test'
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
