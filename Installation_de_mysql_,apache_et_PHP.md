# Installation de mysql ,apache2 et PHP
(devoir de linux du 19 Fevrier 2024)
### Installation de mysql


Télechargeons la version 8.3.0 de mysql sur le site httpd://packages.ubuntu.com
Nous aurons le version compressée mysql.tar.gz

Désarchivons le fichier

    :~$ tar -xvf mysql-8.3.0.tar.gz
    
Puis entrons dans le répertoire de son dossier

    :~$ cd mysql-8.3.0

Exécutons le fichier configure.cmake mais créons un dossier pour faciliter l'exécution

     :~$ mkdir dossier
     :~$ cd dossier
     
On va l'exécuter dans le chemin où se trouve cmakelist.txt

     :~$ cmake ..

Il'y a une erreur en execution du fichier ,il manque ces dépendances

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

 Puis:
 
	:~$ sudo make install
 
pour finir l'installation



### Installation de apache2

Nous avons besoins d'installer ces dépendances :

apr-1.7.4 , apr-util-1.6.3 et pcre-8.00 pour la compatibilité 

Installation de code sources apr-1.7.4

         :~$ tar -xvf apr-1.7.4.tar.gz
         :~$ cd apr-1.7.4
         :~$ ./configure
         :~$ make
         :~$ sudo make install

Installation du code source apr-util-1.6.3.tar.gz

         :~$ tar -xvf apr-util-1.6.3.tar.gz
         :~$ cd apr-1.6.3
         :~$ ./configure  --with-apr=/usr/local/apr
         :~$ make
         :~$ sudo make install

Installation du code source pcre-8.00.tar.gz

         :~$ tar -xvf pcre-8.00.tar.gz
         :~$ cd pcre-8.00
         :~$ ./configure  --with-apr=/usr/local/apr
         :~$ make
         :~$ sudo make install 

  Enfin installons apache2 en suivant ces commandes

         :~$ ./configure --with-apr=/usr/local/apr
	 :~$ make


  S'il y a une erreur dans la compilation il faudra installer les bibliotheques libexpat1-dev et libexport1-dev
  avec 
  
         :~$ sudo apt install libexpat1-dev libexport1-dev

  puis
  
         :~$ sudo make install


