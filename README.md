# Dossier-partage-


# Projet 2 : Dossier partagé Linux

## Objectif
Créer un dossier partagé entre plusieurs utilisateurs avec permissions correctes.

## Utilisateurs et groupe
- etudiant_test
- user2
- Groupe : projet

## Dossier partagé
- /srv/projet_partage
- Permissions : 770
- Setgid actif pour que tous les fichiers héritent du groupe

## Tests
1. Connexion avec etudiant_test
2. Création de test_etudiant.txt
3. Connexion avec user2
4. Création de test_user2.txt
5. Vérification des fichiers et permissions

## Commandes principales
```bash
sudo useradd -m -s /bin/bash etudiant_test
sudo passwd etudiant_test
sudo useradd -m -s /bin/bash user2
sudo passwd user2
sudo groupadd projet
sudo usermod -aG projet etudiant_test
sudo usermod -aG projet user2
sudo mkdir /srv/projet_partage
sudo chown :projet /srv/projet_partage
sudo chmod 2770 /srv/projet_partage
