<<<<<<< HEAD
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
=======
Role Name
=========

A brief description of the role goes here.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
>>>>>>> b19ef85 (Ajout du rôle Ansible Wordpress complet)
