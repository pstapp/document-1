# Nginx on Centos 7
## Setup
  1. Enable EPEL repository  
    `sudo yum install epel-release -y`
  1. Install nginx  
    `sudo yum install nginx -y`

## Service
  1. Enable autostart service  
    `systemctl enable nginx`
  1. Start service  
    `systemctl start nginx`

## Firewall
  - Enable http and https service
```
    sudo firewall-cmd --permanent --add-service=http
    sudo firewall-cmd --permanent --add-service=https
    sudo firewall-cmd --reload
```

## After modify configuration
  1. Verify config  
    `sudo nginx -t`
  2. Restart service  
    `systemctl restart nginx`

## Problem solving 
 - Enable httpd_can_network_connect on selinux  
    `sudo setsebool -P httpd_can_network_connect 1`