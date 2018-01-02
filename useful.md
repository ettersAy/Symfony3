# Useful to know

## GIT

  * To reset all commit 
  ``` git reset --hard origin/master ```
  * To see/get the sha1 id of the commit you want to come back too
  ``` gitk --all ```
  
  * To roll back to that commit
  ``` git reset --hard sha1_id ```
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