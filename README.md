# script_backup_applicatif

## Description
Ce script permet de sauvegarder les fichiers d'une application en créant une archive
tar.bz2 et en le copiant sur un serveur distant

## Utilisation

Utilisation du script :

	
-s	Dossier source de l'application à sauvegarder (sans le / de fin)

-n	Nom du Backup (default: Nom du dossier + YYYY/MM/DD)

-f	Dossier pour la création de l'archive (default: Dossier courant)

-t	Chemin de sauvegarde de l hote distant

-v	Mode verbeux

*******
Exemple
*******

script_backup_applicatif -s /opt/redmine-2.6.0 -n Redmine -t backup@192.168.1.1:/mnt/backup_server

*********
IMPORTANT
*********

Pensez à copier la clef public sur le serveur que vous desirer envoyer le backup ( Pour automatiser la tache de backup)

[user@ordi ~]$ ssh-copy-id -i ~/.ssh/id_dsa.pub root@serveur-distant
