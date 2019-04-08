# ansible-pi-web

Ansible playbook to set up a Debian or Raspbian system to host web apps  
Pulls the laravel repository to set up the new web app  
See the "Installed package section for details"  
Inspired and created thanks to lots of projects found on github.com

## Required
    - Raspberry pi
    - Raspbian stretch lite installed
    - SSH to the pi, key authentication
    - Ansible

## Installed
```shell
- GIT
- ZSH
    - ZSH as default shell for user 'pi'
- Oh My Zsh
- Nginx
    - Server block configuration
    - Clone a git repository in the working directory
    - If laravel app, do the basic laravel app setup
- Php-fpm (7.3)
- MariaDB
    - User creation
    - App database creation
- Composer

- Default php packages list :
    - common
    - cli
    - intl
    #- imagick
    - imap
    - curl
    - cgi
    - fpm
    - mysql
    - gd
    - mbstring
    #- mcrypt Deprecated not installed
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
 - [X] Add an option to deploy a git repo in app folder
 - [ ] Make it compatible with ArchLinux and others
 - [X] Add option to use php or not (static website)
 - [X] Add option to use mariaDB or not (static website)
 - [X] Add composer installation tasks
 - [X] Add Laravel basic setup : install dependencies, create .env file, generate app key, configure directories permissions
 - [ ] Add laravel database basic setup (migrate, setup .env)
 - [ ] Add Adminer role
 - [ ] Improve nginx server block template
 - [X] Add raspbian buster source.list to get php last version
 - [ ] Remove unnecessary become and become_method
 - [ ] Don't use 'shell' module use 'command' instead
 - [ ] Only do laravel basic app setup if it has not already been done
 - [ ] Separate deploy logic at the end .. 

