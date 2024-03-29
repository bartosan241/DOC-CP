**PRISE EN MAIN HOMEASSISTANT**

.. image:: media/image1.png
   :width: 2.28889in
   :height: 2.28889in

**Tableau des matières**

-  **Introduction**

-  **Installation de VSCode**

-  **Installation de Docker**

-  **Configuration de Docker**

-  **Installation de Home Assistant**

-  **Première prise en main**

-  **Conclusion**

1. **Introduction**

**Home Assistant est une plateforme open-source qui permet de contrôler
différents dispositifs domotiques depuis une interface centralisée.
Cette guide détaille le processus d'installation de Home Assistant sur
une machine virtuelle (VM) en utilisant Docker pour la gestion des
conteneurs. Nous commencerons par l'installation de VSCode, un éditeur
de code, suivi par l'installation de Docker et enfin, nous installerons
Home Assistant et explorerons ses fonctionnalités de base.**

|image1|\ |image2|

**2\ . Installation de VSCode**

**Visual Studio Code (VSCode) est un éditeur de code léger, puissant et
open-source, qui fournit des fonctionnalités avancées pour le
développement. Suivez les étapes suivantes pour installer VSCode sur
votre machine virtuelle :**

**Téléchargez le fichier d'installation de VSCode depuis le site
officiel :**

|image3| https://code.visualstudio.com/download

**Choisissez la version compatible avec votre système d'exploitation.**

**Suivez les instructions d'installation fournies sur le site Web.**

**Une fois installé, lancez VSCode pour vous assurer qu'il fonctionne
correctement.**

**3. Installation de Docker**

**Docker permet de déployer des applications dans des conteneurs
logiciels. Voici les étapes pour l'installer sur votre machine virtuelle
en utilisant des lignes de commande Docker :**

-  **Si ce n’est pas encore fait, installer docker sr votre machine via
   la ligne :**

**sudo apt install docker-ce docker-ce-cli containerd.io**

-  **Tester le bon fonctionnement de docker après installation via la
   commande :**

**sudo docker run hello-world**

**Résultat attendu:**

.. image:: media/image4.png
   :alt: Une image contenant texte, capture d’écran, Police Description
   générée automatiquement
   :width: 6.3in
   :height: 2.49375in

-  **Activer le service Docker au démarrage du système Linux**

**sudo systemctl enable docker**

-  **Assurez-vous d'avoir Docker installé en exécutant la commande
   suivante :**

**docker --version**

-  **Pour vérifier si Docker est en cours d'exécution, utilisez la
   commande :**

**docker ps**

-  **Pour vérifier l'état du service Docker, utilisez la commande :**

**sudo systemctl status docker**

**4. Installation de Home Assistant**

**Maintenant que Docker est installé et configuré, passons à
l'installation de Home Assistant :**

**Ouvrez un terminal dans VSCode ou accédez à la ligne de commande de
votre système d'exploitation.**

-  **Créez un répertoire pour Home Assistant en exécutant la commande
   suivante :**

mkdir ~/homeassistant

-  **Accédez au répertoire que vous venez de créer :**

cd ~/homeassistant

-  **Creation fichier docker-compose .yml**

**Crée un fichier nommé docker-compose.yml contenant le code
ci-dessous :**

version: '3'

services:

homeassistant:

container_name: homeassistant

image: "ghcr.io/home-assistant/home-assistant:stable"

volumes:

- ./config:/config

- /etc/localtime:/etc/localtime:ro

restart: unless-stopped

privileged: true

network_mode: host

-  **Lancez le conteneur Home Assistant avec la commande suivante :**

**sudo docker compose up -d**

-  **Afficher les conteneurs lancés :**

**sudo docker ps**

-  **Pour mettre en pause un conteneur Home Assistant :**

docker pause homeassistant

-  **Supprimer un conteneur Home Assistant :**

docker rm homeassistant

**5. Première prise en main**

**Une fois Home Assistant installé, ouvrez un navigateur Web et accédez
à son interface en utilisant l'adresse IP de votre machine virtuelle
suivie du port 8123**

http://localhost:8123/lovelace/default_view

**Suivez les instructions pour configurer votre instance de Home
Assistant. Une fois configuré, explorez le tableau de bord principal
pour ajouter des appareils et automatiser des tâches.**

**6. Conclusion**

**Vous avez désormais installé Home Assistant sur votre machine
virtuelle en utilisant Docker via VSCode. Explorez les fonctionnalités
et les intégrations offertes par Home Assistant pour personnaliser votre
expérience domotique. Pour plus d'informations et d'aide, consultez la
documentation officielle de Home Assistant et Docker.**

.. |image1| image:: media/image1.png
   :width: 2.28889in
   :height: 2.28889in
.. |image2| image:: media/image2.png
   :width: 3.61111in
   :height: 2.02222in
.. |image3| image:: media/image3.png
   :width: 1.55556in
   :height: 1.55556in

