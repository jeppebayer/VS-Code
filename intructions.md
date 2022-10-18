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

GitHub can be very practical for backing up files related to your project, keeping version control, and making information sharing easier. If you want you can create a [GitHub account here](https://github.com/)

https://www.inmotionhosting.com/support/server/ssh/how-to-add-ssh-keys-to-your-github-account/
