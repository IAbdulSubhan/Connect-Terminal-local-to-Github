# Connect Terminal to GitHub using SSH

This guide will help you connect your local terminal to GitHub using SSH. Follow the steps below to set up SSH authentication.
## Step1: Create Directory 
 ```bash
mkdir ~/.ssh
 ```
## Step 2: Navigate to SSH Directory

First, go to the `.ssh` directory:

 ```bash
cd ~/.ssh
 ```

## Step 3: Generate RSA SSH Key Pair

Generate a new RSA SSH key pair:

 ```bash
ssh-keygen -t rsa -b 4096 -C "youremail@gmail.com"
 ```

- When prompted to enter a file name, remember it for later use.
- You will get two files: a private key and a public key.

## Step 4: Add SSH Key to GitHub

1. Open the `.pub` file (public key) and copy the key:

 ```bash
cat ~/.ssh/yourkeyfilename.pub
 ```

2. Go to your GitHub account settings:
   - Navigate to **Settings** > **SSH and GPG keys**.
   - Click on **New SSH key** in the upper right corner.
   - Add a title for the key (you can choose any title).
   - Paste the copied SSH key into the "Key" field.
   - Click **Add SSH key**.

## Step 5: Start the SSH Agent

Start the SSH agent in the background:

 ```bash
eval "$(ssh-agent -s)"
 ```

## Step 6: Add SSH Key to SSH Agent

Add your SSH key to the agent:

 ```bash
ssh-add ~/.ssh/yourkeyfilename
 ```

## Step 7: Verify the SSH Key

Check if the SSH key is added:

 ```bash
ssh-add -l
 ```

## Step 8: Test SSH Connection to GitHub

Test your SSH connection to GitHub:

 ```bash
ssh -T git@github.com
 ```

You should see a message like:

Hi username! You've successfully authenticated, but GitHub does not provide shell access.


This means your SSH setup is complete, and you can now use SSH to interact with your GitHub repositories.

## Troubleshooting

If you encounter any issues, ensure you:

1. Added the correct SSH key to GitHub.
2. Specified the correct path to your private key file.
3. Have the correct permissions set for your SSH key files:

 ```bash
chmod 600 ~/.ssh/yourkeyfilename
chmod 600 ~/.ssh/yourkeyfilename.pub
 ```

For more detailed troubleshooting, refer to GitHub 's [SSH key documentation](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/about-ssh).

---

By following these steps, you will have successfully set up SSH authentication for GitHub. If you encounter any issues, feel free to ask for help!
' > README.md
