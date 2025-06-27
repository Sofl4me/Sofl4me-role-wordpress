# Rôle Ansible pour le déploiement de WordPress avec MariaDB

Ce rôle Ansible permet de déployer automatiquement WordPress avec une base de données MariaDB sur des serveurs Linux (Debian/Ubuntu et Rocky Linux). Il est conçu pour être utilisé dans des environnements conteneurisés.

## Prérequis

- Ansible 2.9 ou supérieur
- Accès root ou sudo sur les machines cibles
- Machines cibles avec Debian/Ubuntu ou Rocky Linux

## Variables

Voici les principales variables à définir pour utiliser ce rôle :

| Variable | Description | Valeur par défaut |
|----------|-------------|-------------------|
| `web_user` | Utilisateur pour les fichiers web | `www-data` pour Debian, `apache` pour RedHat |
| `web_group` | Groupe pour les fichiers web | `www-data` pour Debian, `apache` pour RedHat |
| `mariadb_root_password` | Mot de passe root pour MariaDB | (Aucune valeur par défaut) |
| `wordpress_db_name` | Nom de la base de données WordPress | `wordpress` |
| `wordpress_db_user` | Utilisateur de la base de données WordPress | `wordpress_user` |
| `wordpress_db_password` | Mot de passe de l'utilisateur de la base de données WordPress | (Aucune valeur par défaut) |

## Exemple de Playbook

Voici un exemple de playbook pour utiliser ce rôle :

```yaml
---
- hosts: all
  become: true
  vars:
    mariadb_root_password: "votre_mot_de_passe_root"
    wordpress_db_password: "votre_mot_de_passe_wordpress"
  roles:
    - role: votre_role_wordpress
