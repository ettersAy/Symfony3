# Useful to know

## GIT

### Steps to start a new sprint
  * Create a new branch (example: sprint24) from develop.
```
    git checkout develop
    git pull
    git checkout -b sprint24
    git push --set-upstream origin sprint24
```
  * Create a branch, from sprint24 branch, for every ticket.
```
    git checkout sprint24
    git pull
    git checkout -b feature/newTicket
    git push --set-upstream origin feature/newTicket
```
### Steps to put into prodection
  * Merge all branch of sprint tickets with branch sprint24
  ```
        git checkout sprint24
        git merge feature/nom-branche
        git add CHANGELOG.md
        git commit -m"CHANGELOG.md"
        git push
  ```
  * Merger (sprint24) with develop
  ```
        git checkout develop
        git pull
        git merge sprint24
        git push
  ```
  * merge develop with master
 ```
        git checkout master
        git pull
        git merge develop
        git push
        git tag 1.12.21
        git push --tags
```
### Some useful commands
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
