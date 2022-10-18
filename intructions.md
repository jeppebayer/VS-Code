# Instructions

## Setting up ssh authentication keys

Use the following command to generate a pair of authentication keys. When asked "Enter file in which to save the key" just press enter. When prompted to enter a passphrase, just press enter.

On local machine:

```bash
ssh-keygen -t rsa
```

Now to create a directory for the public key on the cluster. You will be prompted to enter your password.

On local machine:

```bash
ssh <cluster_username>@login.genome.au.dk mkdir -p .ssh
```

Now we append the public `ssh` key on your local machine to the file `.ssh/authorized_keys` on the cluster. You will be asked to enter your password.

On local machine:

```bash
cat ~/.ssh/id_rsa.pub | ssh username@login.genome.au.dk 'cat >> .ssh/authorized_keys'
```

From now on you can log into the cluster from your local machine without being prompted for a password.

## GitHub

GitHub can be very practical for backing up files related to your project, keeping version control, and making information sharing easier. If you want you can create a [GitHub account here](https://github.com/).  
To add your ssh keys to GitHub intructions can be found [here](https://www.inmotionhosting.com/support/server/ssh/how-to-add-ssh-keys-to-your-github-account/).

### Git

[Git](https://git-scm.com/) is a version control tool that you can use from the terminal

While logged into the cluster run these two commands and let Git know who you are:

```bash
git config --global user.name "<your_github_username>"
git config --global user.email <your_email@whatever.com>
```

## Visual Studio Code

[VS Code](https://code.visualstudio.com/) is great for developing scripts and editing text files. Once you have installed VS Code, you should install the "Remote Development" extension. You do that by clicking the funny squares in the left bar and search for "Remote Development". Once installed, you can click the small green square in the lower-left corner to connect to the cluster. Select "Connect current window to host" then "Add new SSH host", then type `<username>@login.genome.au.dk`, then select the config file `.ssh/config`. Now you can click the small green square in the lower-left corner to connect to the cluster by selecting `login.genome.au.dk`. It may take a bit, but once it is done installing a remote server, you will have access to the files in your home folder on the cluster.
