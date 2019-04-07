# ansible-pi-web

Ansible playbook to set up a Debian or Raspbian system to host web apps  
Pulls the laravel repository to set up the new web app  
See the "Installed package section for details"  

## Required
    - A raspberry pi
    - Raspbian stretch lite installed on a pi
    - SSH to the pi (with key authentification enabled)
    - Ansible

## Installed packages
```shell
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
```

## Usage
Edit your hosts configurations
`cp hosts.example hosts`  
Edit `hosts` file with your desired hosts and your local sudo password to allow editing the local /etc/hosts file to access nginx server block from the local host (the one that runs ansible playbook)
Run the playbook
`ansible-playbook -i hosts playbook.yml`  

## Improvements ideas
 - [X] Add an option to auto deploy a git repo in app folder
 - [ ] Make it compatible with ArchLinux and others
 - [X] Add option to wether use php or not (static website)
 - [ ] Add option to whether use mariaDB or not (static website)
 - [X] Add composer installation tasks
 - [X] Add Laravel basic setup : install dependencies, create .env file, generate app key, configure direcotries permissions
 - [ ] Add database handling laravel basic setup (migrate, setup .env with db connection)
 - [ ] Add Adminer
 - [ ] Improve nginx server block template
 - [X] After testing raspbian stretch comes with php 7.0 which is not enough for laravel last version we will have to add the new repo to source.list >> buster
 - [ ] Remove unnecessary become and become_method
 - [X] Clear vars
 - [ ] Don't use 'shell' module use 'command' instead
 - [ ] Only do laravel basic app setup if it has not already been done
 - [ ] Add database setup in .env file and basic setup in deploy.yml to migrate database and seed
 - [ ] Separate deploy logic at the end .. 

