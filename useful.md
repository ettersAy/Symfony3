# Useful to know
## Mysql
  * Select last 6 months
```
    SELECT id, sent from CONTACT where sent > DATE_SUB(NOW(), INTERVAL 6 MONTH);
```
## GIT

### Steps to start a new sprint
  * Create a new branch from develop (example: sprint24).
```
    git checkout develop
    git pull
    git checkout -b sprint24
    git push --set-upstream origin sprint24
```
  * Create a branch for every ticket, from sprint24 branch (example: feature/newTicket).
```
    git checkout sprint24
    git pull
    git checkout -b feature/newTicket
    git push --set-upstream origin feature/newTicket
```
### Steps to put into prodection
  * Merge all branch tickets of sprint with the root sprint24 branch.
  ```
        git checkout sprint24
        git merge feature/name-branche
        git merge feature/name-branche2
        git push
  ```
  * Merger (sprint24) with develop.
  ```
        git checkout develop
        git pull
        git merge sprint24
        git push
  ```
  * Add notable changes in `CHANGELOG.md`. Merge develop with master. 
 ```
        git checkout master
        git pull
        git merge develop
        git add CHANGELOG.md
        git commit -m "CHANGELOG.md"
        git push
        git tag 1.15.3
        git push --tags
```
### Some useful commands
  * Initialize a new repository.
```
    echo "# NewRepos" >> README.md
    git init
    git add README.md
    git commit -m "first commit"
    git remote add origin git@github.com:ettersAy/NewRepos.git
    git push -u origin master
```

  * To reset all commit 
``` 
        git reset --hard origin/master 
```
  * To see/get the sha1 id of the commit you want to come back too
```
        gitk --all 
```
  
  * To roll back to that commit
``` 
        git reset --hard sha1_id 
```
  
  * Delete a remote Git tag
``` 
        git tag -d 1.01.1
        git push origin :refs/tags/1.01.1 
```
  
  * Push removed files 
``` 
        git add . -A 
        git commit -m "removed some files"
        git push
```  
  * Push ignored file by `.gitignore`.
``` 
        git add -f var/sessions/.gitkeep
```
## LINUX

### Generating a new SSH key
  * creates a new ssh key, using the provided email as a label.
``` 
        ssh-keygen -t rsa -b 4096 -C "your_email@example.com" 
        Enter a file in which to save the key (/c/Users/you/.ssh/id_rsa):[Press enter] 
        Enter passphrase (empty for no passphrase): [Type a passphrase]
        Enter same passphrase again: [Type passphrase again] 
``` 
  * start the ssh-agent in the background
``` 
        eval $(ssh-agent -s) 
```
  * Add your SSH private key to the ssh-agent.
``` 
        ssh-add ~/.ssh/id_rsa 
```
  * Download file.
``` 
        curl -LO 'https://symfony.com/installer' 
        OR 
        wget https://symfony.com/installer
```
    * Change the access permissions.
``` 
        sudo chmod 777 -R var
```
    * Redirect errors commande to log file
``` 
        find -name *test* 2> /tmp/out.log
```
## Symfony

### Create new project
  * Download symfony.phar
```
    https://symfony.com/installer
```
    * Create a new project
```
    php symfony.phar new nameProject 3.3.2
    cd nameProject
    rm -rf var/*
    sudo chmod 777 -R var
    php bin/console assets:install
    http://localhost/Symfony/web/app_dev.php/
```

### Install Symfony 2
  * Install intl extension
``` 
       yum list php*intl
       sudo yum install php70w-intl.x86_64
``` 
  * Install pecl extension
``` 
       yum list *pecl*
       sudo yum install php70w-pecl-apcu.x86_64
``` 
  * Install opcache extension 
``` 
       yum list *opcache*
       sudo yum install php70w-opcache.x86_64
``` 
  * Config opcache extension : http://symfony.com/doc/2.7/performance.html
``` 
       sudo vi /etc/php-zts.d/opcache.ini 
       ; maximum memory that OPcache can use to store compiled PHP files
       opcache.memory_consumption=256
       ; maximum number of files that can be stored in the cache
       opcache.max_accelerated_files=20000
       opcache.validate_timestamps=0

       Sudo vi /etc/php.ini
       ; maximum memory allocated to store the results
       realpath_cache_size=4096K
       ; save the results for 10 minutes (600 seconds)
       realpath_cache_ttl=600

       cd /usr/lib64/php/modules
``` 
  * Check systeme
``` 
       php app/check.php 
       or 
       http://localhost/symfony2.7/web/config.php
       
``` 
## Docker
  * The principal advantage
```
    The principal advantage of docker: is the fact that every team member work with the same environment, which is the copy of production environment.
```
## MySQL
  * Connecting to the MySQL Server
```
        shell> mysql --host=localhost --user=myname --password mydb
        shell> mysql -h localhost -u myname -p mydb
```
