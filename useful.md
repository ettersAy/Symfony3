# Useful to know

## GIT

### Steps to start sprint
  * Créer une nouvelle branch, depuis le develop, pour le sprint en cours exemple (sprint24)
```
    git checkout develop
    git pull
    git checkout -b sprint24
    git push --set-upstream origin newBranch
```
  * Pour chaque ticket une branch
```
    git checkout sprint24
    git pull
    git checkout -b newTicket
    git push --set-upstream origin newTicket
```
### Les étapes d'une mise en prod (MEP)
  * merger les branch du ticket exemple (feature/nom-branche) avec la branch sprint24
  ```
        git checkout sprint24
        git merge feature/nom-branche
        git add CHANGELOG.md
        git commit -m"CHANGELOG.md"
        git push
  ```
  * merger (sprint24) avec develop
  ```
        git checkout develop
        git pull
        git merge sprint24
        git push
  ```
  * merge develop avec master
 ```
        git checkout master
        git pull
        git merge develop
        git push
        git tag 1.12.21
        git push --tags
```
### Some     
  * To reset all commit 
  ``` git reset --hard origin/master ```
  * To see/get the sha1 id of the commit you want to come back too
  ``` gitk --all ```
  
  * To roll back to that commit
  ``` git reset --hard sha1_id ```
  
  * Delete a remote Git tag
  ``` 
  git tag -d 1.01.1
  git push origin :refs/tags/1.01.1 
```
## LINUX

### Generating a new SSH key
  * creates a new ssh key, using the provided email as a label.
  ``` 
  ssh-keygen -t rsa -b 4096 -C "your_email@example.com" 
  ``` 
  * Press Enter. This accepts the default file location.
  ``` 
  Enter a file in which to save the key (/c/Users/you/.ssh/id_rsa):[Press enter] 
  ``` 
  * Press Enter.
  ```
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
  * 
  ``` ``` 
