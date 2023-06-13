# sshrepo
This Notes will help you on how to easily setup your CLI ssh keys and push your files to GitHub (Passwordless Authentication)
NOTE: SSH remote URL is different from https and it's mostly used on Linux CLI.
Here we are using ssh: git@github.com:Ngwaabanjong/sshrepo.git

Basically git can communicate with GitHub over https or SSH.
Username and personal access token are required to push files into repo by authenticating the user.

# Method:
************************
When git is connected to github over SSH

# Step 1:
For this process on the local machine you will have to generate :

SSH private key
SSH public key

The command to generate SSH key is: ssh-keygen -t rsa -b 2048 = -t for type and -b for bit.

Come out of your repo to your home directory $ pwd

$ ssh-keygen -t rsa -b 2048

Press enter key 3 times to avoid passphrase.

The key will be generated and public key will be in /root/.ssh/id_rsa.pub

Get the public key content

$ cat /root/.ssh/id_rsa.pub

You will then copy the public key 

ssh-rsa AAvNPGoj6mk+mW4lofMejkYeC/E5Yzhnx/Yn4LvP1ptXzzg1WOLICe//PJ7QI
n7lCuQa79ce+PSvWOS7auYQN+8SwNC2U+oW/ZbK1NnsPvD/IcMyjyRyFshuEeHuL+WY7wK
f+QBmGUlFlQuP root@ip-172-31-22-204.us-east-2.compute.internal

# Step 2:
On GITHUb

GITHUB -> Settings -> leftside click on SSH & GPG keys -> click on new SSh key 
Give title of key. 
Pasted the copied key in next box, 
Save. 

By this method github now identifies you local machine as a authenticated user
Now you don't have to give any username or personal access token while pushing files into github.

# Step 3:
On CLI:

$ git config --global user.name "your_name"
$ git config --global user.email "email@address.com"

Remember the remote URL for the repo will look like this: git@github.com:Ngwaabanjong/sshrepo.git

$ git clone git@github.com:Ngwaabanjong/sshrepo.git

Create and modify files.
$ git add .
$ git commit -m "comment"
$ git push origin master

End
************************************************************************
Gimme a star if it helped :)

Produced by: Ignatius Ngwaabanjong
