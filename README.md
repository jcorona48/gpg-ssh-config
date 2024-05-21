# GPG and SSH

This repository is for those who want their commits to be verified.

You can easily configure it by following these steps...

## Basic Git Configuration

```bash
git config --global user.name "Your Name"
```

```bash
git config --global user.email name@example.com
```

```bash
git config --global core.editor "code --wait"
```

```bash
git config --global core.autocrlf input
```

## Configure SSH
### Generate SSH Key

```bash
ssh-keygen -t rsa -b 4096 -C "name@example.com"
```
### Retrieve SSH Key
```bash
cat ~/.ssh/id_rsa.pub
```

### Go to GitHub and add the SSH key

### Test Connection
```bash
ssh -T git@github.com
```

## Configure GPG

### Generate GPG Key
```bash
gpg --full-generate-key
```

### Get GPG Key ID

```bash
gpg --list-secret-keys --keyid-format=long
```

Copy the code that appears after the slash in the "sec" section.

Example

3AA5C34371567BD2 

### Get GPG Key for GitHub

```bash
gpg --armor --export 3AA5C34371567BD2
```

### Configure GPG Key in GitHub


## Tell Git to sign your commits with GPG

### Configure Git to use GPG
```bash
git config --global --unset gpg.format
```

### Get GPG Key ID 
```bash
gpg --list-secret-keys --keyid-format=long
```

### Configure GPG Key for Git

```bash
git config --global user.signingkey 3AA5C34371567BD2
```

### Sign commits with GPG
```bash
git config --global commit.gpgsign true
```
