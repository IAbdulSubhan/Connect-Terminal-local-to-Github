# Connect Terminal to GitHub using SSH

This guide will help you connect your local terminal to GitHub using SSH. Follow the steps below to set up SSH authentication.

## Step 1: Navigate to SSH Directory

First, go to the `.ssh` directory:

```bash
cd ~/.ssh


## Step 2: Generate RSA SSH Key Pair
Generate a new RSA SSH key pair:

```bash
ssh-keygen -t rsa -b 4096 -C "youremail@gmail.com"


* When prompted to enter a file name, remember it for later use.
* You will get two files: a private key and a public key.

## Step 3: Add SSH Key to GitHub
1: Open the .pub file (public key) and copy the key:

```bash
cat ~/.ssh/yourkeyfilename.pub

2: Go to your GitHub account settings:

* Navigate to Settings > SSH and GPG keys.
* Click on New SSH key in the upper right corner.
* Add a title for the key (you can choose any title).
* Paste the copied SSH key into the "Key" field.
* Click Add SSH key.

## Step 4: Start the SSH Agent

Start the SSH agent in the background:

```bash
eval "$(ssh-agent -s)"


## Step 5: Add SSH Key to SSH Agent

Add your SSH key to the agent:

```bash
ssh-add ~/.ssh/yourkeyfilename


## Step 6: Verify the SSH Key

Check if the SSH key is added:

```bash
ssh-add -l

## Step 7: Test SSH Connection to GitHub

Test your SSH connection to GitHub:

```bash
ssh -T git@github.com


#### You should see a message like:

```bash
Hi username! You've successfully authenticated, but GitHub does not provide shell access.


This means your SSH setup is complete, and you can now use SSH to interact with your GitHub repositories.


