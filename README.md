# script_backup_applicatif

## Description
Ce script permet de sauvegarder les fichiers d'une application en créant une archive
et de la copier sur un serveur distant

## Utilisation

Utilisation du script :

	
-s	Dossier source de l'application à sauvegarder (sans le / de fin)

-n	Nom du Backup (default: Nom du dossier + YYYY/MM/DD)

-f	Dossier pour la création de l'archive (default: Dossier courant)

-t	Chemin de sauvegarde de l hote distant

-P	Port SSH de l hote distant (default : 22)

-z  Compression au format ZIP au lieu de tar.bz2

-k  Garder la sauvegarde en local si l'option de transfert est activée

-v	Mode verbeux


## Exemple

### TAR.BZ2

Si l'on veut transférer la sauvegarde:

```sh
script_backup_applicatif -s /opt/redmine-2.6.0 -n Redmine -t backup@192.168.1.1:/mnt/backup_server
```

Si l'on veut une sauvegarde en local:

```sh
script_backup_applicatif -s /opt/redmine-2.6.0 -n Redmine -f /opt/backup/Redmine
```

### ZIP

Si l'on veut transférer la sauvegarde

```sh
script_backup_applicatif -z -s /opt/redmine-2.6.0 -n Redmine -t backup@192.168.1.1:/mnt/backup_server
```

Si l'on veut une sauvegarde en local

```sh
script_backup_applicatif -z -s /opt/redmine-2.6.0 -n Redmine -f /opt/backup/Redmine
```

*********
IMPORTANT
*********

Pensez à copier la clef public sur le serveur que vous desirer envoyer le backup ( Pour automatiser la tache de backup)

```sh
[user@ordi ~]$ ssh-copy-id -i ~/.ssh/id_dsa.pub root@serveur-distant
```
