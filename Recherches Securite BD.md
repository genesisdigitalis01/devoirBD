# Exercice de recherche  sur la sécurisation des Bases de données 

# EXERCICE 1 : Les Cyberattaques

Attaques par déni de service (DoS) et par déni de service distribué (DDoS)
Attaque de l’homme au milieu (MitM)
Hameçonnage (phishing) et harponnage (spear phishing)
Téléchargement furtif (drive-by download)
Cassage de mot de passe
Injection SQL
Cross-site scripting (XSS)
Écoute clandestine
Attaque des anniversaires
Logiciel malveillant (malware)

Celles concernant les bases de données :

- Cross-site scripting (XSS) : 
Les attaques XSS utilisent des ressources Web tierces pour exécuter des scripts dans le navigateur Web de la victime ou dans une application pouvant être scriptée. Plus précisément, l’attaquant injecte un JavaScript malveillant dans la base de données d’un site Web. Lorsque la victime demande une page du site Web, le site Web transmet la page à son navigateur avec le script malveillant intégré au corps HTML. Le navigateur de la victime exécute ce script, qui envoie par exemple le cookie de la victime au serveur de l’attaquant, qui l’extrait et l’utilise pour détourner la session. Les conséquences les plus graves se produisent lorsque XSS sert à exploiter des vulnérabilités supplémentaires. Ces vulnérabilités peuvent non seulement permettre à un attaquant de voler des cookies, mais aussi d’enregistrer les frappes de touches et des captures d’écran, de découvrir et de collecter des informations réseau et d’accéder et de contrôler à distance l’ordinateur de la victime.

- Injection SQL : 
L’injection SQL est devenue un problème courant qui affecte les sites Web exploitant des bases de données. Elle se produit lorsqu’un malfaiteur exécute une requête SQL sur la base de données via les données entrantes du client au serveur. Des commandes SQL sont insérées dans la saisie du plan de données (par exemple, à la place du nom d’utilisateur ou du mot de passe) afin d’exécuter des commandes SQL prédéfinies. Un exploit d’injection SQL réussi peut lire les données sensibles de la base de données, modifier (insérer, mettre à jour ou supprimer) les données de la base de données, exécuter des opérations d’administration de la base de données (par exemple la fermer), récupérer le contenu d’un fichier spécifique, et, dans certains cas, envoyer des commandes au système d’exploitation.

- Logiciel malveillant (malware) : 
Un logiciel malveillant peut être décrit comme un logiciel indésirable installé dans votre système sans votre consentement. Il peut s’attacher à un code légitime et se propager, se cacher dans des applications utiles ou se reproduire sur Internet. Voici quelques-uns des types de logiciels malveillants les plus courants : Macro-virus, Infecteurs de fichiers, Infecteurs de système ou de secteur d’amorçage, Virus polymorphes, Virus furtifs, Chevaux de Troie, Bombe logique, Injecteurs, Rançongiciels (ransomware).

# EXERCICE 2 : Definition de la Politique de sécurité par l'ITSEC

L'ITSEC définit la politique de sécurité des systèmes d'information (PSSI) comme un plan d'actions définies pour maintenir un certain niveau de sécurité. Elle reflète la vision stratégique de la direction de l'organisme (PME, PMI, industrie, administration, État, unions d'États…) en matière de sécurité des systèmes d'information (SSI).
La politique de sécurité des systèmes d'information est intrinsèquement liée à la sécurité de l'information.
Aussi, un système d'information n'étant pas limité au système informatique, une politique de sécurité des systèmes d'information ne se limite pas à la sécurité informatique.


# EXERCICE 3 : Fichiers de Destinations de Sauvegardes des SGBD

### MYSQL

Les fichiers correspondant aux bases de données créées se trouvent dans le répertoire d'installation de MySQL, dans le sous répertoire "data". Ce sont des fichiers .frm et .ibd.

L'extension pourrait aussi dépendre du moteur de base de données utilisé. Les 2 moteurs les plus utilisés sont : MyISAM et InnoDB.

MyISAM est le moteur de table par défaut;

1. MySQL stocke les tables MyISAM dans un dossier portant le nom de la base de données. Par exemple la table wp_options d'une base nommée pstuto sera stockée dans 3 fichiers :

* C:\EasyPHP\mysql\data\pstuto\wp_options.frm
* C:\EasyPHP\mysql\data\pstuto\wp_options.MYD
* C:\EasyPHP\mysql\data\pstuto\wp_options.MYI


1. InnoDB et le fichier ibdata1
InnoDB a un fonctionnement totalement différent. C'est bien simple : InnoDB stocke tout dans un seul et même fichier : bases, tables, indexes. Ce fichier s'appelle ibdata1, il se trouve au même endroit que les fichiers MyISAM :

* C:\EasyPHP\mysql\data\ibdata1

1. Sous Windows et avec WampServer, une base de données se trouve ici : "c:\Wamp\bin\mysql\mysql5.7.13\data".
Si une base se nomme 'essai', elle sera dans un répertoire de nom 'essai'.


## SQLSERVER

SQL Server bases de données ont trois types de fichiers:

   'Principal' : Contient les informations de démarrage de la base de données et pointe vers les autres fichiers de la base de données. L'extension de fichier est .mdf.

 'Secondary' : Les données peuvent être réparties sur plusieurs disques en plaçant chaque fichier sur un lecteur de disque différent. L'extension de fichier est .ndf.

 'Transactions log' : Ce journal contient les informations utilisées pour la récupération de la base de données. Chaque base de données doit posséder au moins un fichier journal. L'extension de fichier est .ldf


## POSTGRESSQL 

Traditionnellement, les fichiers de configuration et les fichiers de données utilisés par une instance du serveur sont stockés ensemble dans le répertoire des données, habituellement référencé en tant que PGDATA (d'après le nom de la variable d'environnement qui peut être utilisé pour le définir). Un emplacement courant pour PGDATA est /var/lib/pgsql/data


## ORACLE 

Les fichiers journaux du serveur Oracle Database se trouvent dans le répertoire /var/opt/SUNWscor/oracle_server.

Les fichiers journaux du listener Oracle Database se trouvent dans le répertoire /var/opt/SUNWscor/oracle_listener.

Le fichier journal d'Oracle ASM se trouvent dans le répertoire /var/opt/SUNWscor/oracle_asm.




# EXERCICE 4 : BRATA


BRATA, l’un des malwares Android les plus dangereux au monde, se dote d’une mise à jour capable de faire encore plus de dégâts. Alors qu’il pouvait déjà siphonner les comptes bancaires de ses victimes et supprimer toutes les données du smartphone cible, il espionne désormais les messages de clients de banques spécifiques pour récupérer leurs identifiants.
La première fois que nous vous en avons parlé, c’était en 2021. BRATA venait alors d’être découvert par des chercheurs de Cleafy, au même moment de son arrivée en Europe. Son fonctionnement faisait déjà froid dans le dos : par le biais d’une campagne de phishing, les pirates parviennent à convaincre leur victime de télécharger leur malware, qu’ils camouflent en fausse application anti-spam. Une fois installé, l’utilisateur perd le contrôle de son smartphone, donnant ainsi accès à ses coordonnées bancaires.