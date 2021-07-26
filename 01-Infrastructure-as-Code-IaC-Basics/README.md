

# Infrastructure as Code Basics

## Step-01: Understand Problems with Traditional way of Managing Infrastructure
- Time it takes for building multiple environments
- Issues we face with different environments
- Scale-Up and Scale-Down On-Demand

## Step-02: Discuss how IaC with Terraform Solves them
- Visibility
- Stability
- Scalability
- Security
- Audit

## This is my first edit to a file before adding and committing then pushing the repo to the github.

01. Edit file.
02. Add file to git for monitoring/tracking using git add . or git add <filname>.
03. Use git commit to apply changes made. This sends tracked files to a staging area which will then be uploaded during the git push command.
04. Use git push to send all local repo changes up to the github cloud. 
05. Don't forget to add credentials before trying to update your github repository. otherwise you won't have permissions to change the github repo.
06. Best to use SSH keys in order to do this if possible.

# Setting up SSH
01. Setup Keypair

```
	ssh-keygen -t rsa - b 4096 -C "email@example.com"

```
	
The file will be saved to /Users/Jay/.ssh/id_rsa or create a new key name file like testkey
optionally add password for key.

2 files will be created.
testkey 
testkey.pub

02. Copy the pub key to the github repostiory
	settings / ssh and gpg keys / new ssh key / title it / paste public key here.

03. Add ssh key to ssh-agent on your laptop
	01. Start ssh-agent
	02. modify .ssh/config file to load all private keys into ssh-agent on startup.

```	

	Host *
	AddKeysToAgent yes
	UseKeyChain yes
	IdentityFile ~/.ssh/<key file>

```
eg. IdentityFile ~/.ssh/testkey

03. Add private key into ssh-agent and store passphrase in the keychain.
		
```
	ssh-add -K ~/.ssh/<keyfile>

```
eg. ssh-add -K ~/.ssh/testkey


