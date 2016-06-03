---
layout: post
title: Setup SSH on linux with github (for dummies)
subtitle: Yes, I consider myself a dummy
---

lets be real, if you've been using an http remote to push your commits to github you probably already hate your life for having to keep re-entering your username and password ALL THE GODDAMNED TIME!  
   
But...what if it didn't have to be that way? What if there was an easier way to do this? What if... *gasp* what if you used SSH?

Okay enough of me being a drama llama preacher of all things good about SSH. Lets get cracking. 
  
This tutorial is meant for linux users. 

### Lets get started!
  
open up a terminal window (you can open a terminal by typing ctrl+alt+t)

```
# run ssh-keygen and press enter for the default values
$ ssh-keygen

# find the rsa_id.pub file in .ssh
$ cat ~/.ssh/id_rsa.pub
```
Now copy the contents of the output of the termial, it'll look something like:

~~~
ssh-rsa AAAAB3NzaC1yc2EAAAAASDLKAJWDLAABAAABAQCxTTNyg6uVyRcdc//GdQwsz/zKculMFkkvdZjfnH4v7vGkTkyXVZ2Mq4nWZzQN33TAEu/Rf062CtwptY3Rl7cxArKl2lc0LNPb6su36MDKDVfTZzs5mdL5l65yvbHEzlmx7nOQL3p7THzuqQq95oCVh1/F2CBr5KYV+88m/CLWrLwxSmr7sZaBbhs/UnvquuFyWCa4cHM/YgLs3+ke/JmSHIptXcHXPMHzMxNhPCB7n76jqHXfADNAJWKDNAKJWDP/KzuuatjOYpCpVdkW/qwVd+u14i9K9jeMvILyxJkZ6yBkzMJtsy6hF5NPTfSAMz6aNFNtlwZNNAbQHlOOIj/ZieNa3uX yourusername@yourprofile
~~~

Log in to your github account and click the top right corner on the dropdown menu, click on 'Settings'.   

go to 'SSH and GPG keys'  

click on 'New SSH Key'

Give your SSH key a name (something like your computer name) and paste the output of the terminal in the box below it.
   
click 'Add SSH Key'
   
#### If you already have an http remote added:
Now if you've already been pushing commits to your existing repository you'll need to reset the origin url which you use to push. You can see your current remotes by typing. 

~~~ 
$ git remote -v 
~~~

in your project's root folder where you initialized your git repository. 
   
Open up your project's github page and copy the ssh url. 
   
Switch back to your terminal again and inside your project's root directory type:

~~~
$ git remote set-url origin master <paste the ssh url here>
~~~
  
  
#### If you're starting a new repository:
This is easier, all you have to do is copy the ssh url for the remote, open up your terminal and type:

~~~
$ git remote add origin <paste the ssh url here>
~~~
  
Aaaaanddd you're done! Wasn't that easy? Now whenever you push to your origin remote it wont ask you for your username and password since you're already authenticated via SSH.



