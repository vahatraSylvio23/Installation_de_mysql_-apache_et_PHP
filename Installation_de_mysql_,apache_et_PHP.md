# Installation de mysql ,apache et PHP

### Installation de mysql

(devoir de linux du 19 Fevrier 2024)

1ère etape: Installation de mysql
Telechargeons la version 8.3.0 de mysql sur le site httpd://packages.ubuntu.com
Nous aurons le version compressée mysql.tar.gz

Desarchivons le fichier
   :~$ tar -xvf mysql-8.3.0.tar.gz

Puis entrons dans le repertoire de son dossier
    :~$ cd mysql-8.3.0

Exécutons le fichier configure.cmake mais créons un dossier pour faciliter l'exécution

     :~$ mkdir dossier
     :~$ cd dossier
On va l'executer dans le chemin où se trouve cmakelist.txt

     :~$ cmake ..

Il'y a une erreur en execution du fichier ,il manque ces dépendences

Téléchargeons ces dependences sur  httpd://packages.ubuntu.com
Ce sont : openssl ,ncurses et libssl3 

Installons ces fichiers après désarchivage en faisant chacun en executant ces commandes:


       :~$ cd nom_paquet
	   
       :~$ ./configure
	   
       :~$ make
	   
       :~$ sudo make install
	   

Une fois les installations de ces paquets terminée


On revient dans le dossier de mysql-8.3.0 dans le dossier


        :~$ cmake  ..

 Après, on va compiler les source avec la commande :

        :~$ make
	:~$ make install
