# ansible-pi-web

Set up a raspberry pi with a fresh raspbian stretch lite installed on it to become a web server capable of hosting php web apps
Pulls a git repository to set up the web app

## Required
    - A raspberry pi
    - Raspbian stretch lite installed freshly on the pi
    - SSH to the pi (with key authentification enabled)
    - Ansible

## Installed packages
    - GIT
    - ZSH (and changed to default shell for user 'pi')
    - Oh My Zsh
    - Nginx
    - Php-fpm
    - MariaDB

    - Php packages list :
        - common
        - cli
        - intl
        - imagick
        - imap
        - curl
        - cgi
        - fpm
        - mysql
        - gd
        - mbstring
        - mcrypt
        - memcached
        - apcu
        - json
        - xml
        - zip

## Set up
    cp hosts.example hosts
Edit 'hosts' file with your desired hosts and your local sudo password to allow editing the local /etc/hosts file to access nginx server block from local host (the one that runs ansible playbook)
