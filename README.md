# jpscanvf
Utilitaire écrit en bash afin d'enregistrer les scans d'un manga sur le site jpscan-vf.com !

# Informations à prendre en compte
Ce script étant écrit en bash (Linux), il ne sera pas possible de l'utiliser sous MacOS ou Windows, a moins de passer par un émulateur ou les applications Ubuntu (ou dérivés basés sur Debian), disponible via le Microsoft Store !
Pour le moment, seul les fichiers étant sur la plateforme http://funquizzes.fun/ (plateforme d'hébérgement) sont compatibles avec ce script (temporairement, le temps de voir si d'autres mangas sont sur d'autres hébérgeurs que http://funquizzes.fun//uploads/manga/)

!!!! IMPORTANT !!!! POUR LE NOM DU MANGA (DOSSIER), ASSUREZ-VOUS D'AVOIR LE MEME NOM SANS FAUTES QUE VOUS POUVEZ TROUVER SUR http://funquizzes.fun/ !!!! (DETAILS A VENIR)

# Execution depuis un dossier programme
Vous pouvez importer (ou plutôt déplacer) le fichier jpscanvf dans /usr/local/bin/) ! Cela vous permettra de faire appel au script ou que vous soyez situé dans votre console !
N'oubliez pas de faire un ``sudo chmod a+x /usr/local/bin/jpscanvf`` afin de donner la permission d'exécuter le script ! 

# Ca ne fonctionne pas ! Pourquoi ?
Dans ce cas je vous invite a modifier une seule chose dans le script:
```
sudo nano /usr/local/bin/jpscanvf
```
Et d'y ajouter ``-q`` devant les wget (lignes 28 et 34)

Vous verrez à l'écran lors de la prochaine tentatives les retours du téléchargement !

# ERREURS ERREURS QUE DES ERREURS !!!
Étant donné que ce script était destiné à usage privé, le code sur GitHub a été adapté a un usage plus général (contrairement à mon cas qui demandait des régalages un peu plus spécifiques) ! Si quelque chose ne se déroule pas comme prévu, merci d'aller dans le salon issues ou me contacter sur Discord (SaigoNoo#3044)

Merci ^^
