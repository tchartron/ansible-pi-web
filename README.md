# ansible-pi-web

Ansible playbook to set up a Debian or Raspbian system to host web apps\s
Pulls the laravel repository to set up the new web app\s
See the "Installed package section for details"\s

## Required
    - A raspberry pi
    - Raspbian stretch lite installed on a pi
    - SSH to the pi (with key authentification enabled)
    - Ansible

## Installed packages
    - GIT
    - ZSH (and changed to default shell for user 'pi')
    - Oh My Zsh
    - Nginx
    - Php-fpm
    - MariaDB
    - Composer

    - Default php packages list :
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
`cp hosts.example hosts`\s
Edit `hosts` file with your desired hosts and your local sudo password to allow editing the local /etc/hosts file to access nginx server block from the local host (the one that runs ansible playbook)

## Improvements ideas
 - [ ] Add option for which repo to pull
 - [ ] Add a laravel version option
 - [ ] Make it compatible with ArchLinux / Manjaro
 - [ ] Add option to wether use php or not (static website)
 - [ ] Add option to whether use mariaDB or not (static website)
 - [ ] Add composer installation tasks
 - [ ] Add Laravel utils like generating app key, migrating database, ...
