# ansible-pi-web

Set up a raspberry pi with a fresh raspbian stretch lite installed on it to become a web server capable of hosting php web apps

## Required
    - A raspberry pi (tested on 3b+)
    - Raspbian stretch lite installed freshly on the pi
    - SSH to the pi (with key)

## Set up
`cp hosts.example hosts`
Edit hosts file with your desired hosts and your local sudo password to allow editing the local /etc/hosts file to access nginx server block from local host
