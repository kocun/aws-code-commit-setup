# Amazon Code Commit Setup
By @adilatilgan
---
>**Note : **  This is for Mac/ Linux users

This is official AWS Code Commit setup for developers. 
>**Note : **  You have to be a member of development team.

First you need to create private and public key

```
cd ~/.ssh
ssh-keygen
[here just create the name aws_rsa and leave all fields blank *just click enter*]
pbcopy aws_rsa.pub
```

Then you should commit aws_rsa.pub to IAM.

Goto IAM/Users/Security Credentials Screen and click **Upload SSH Key** then paste your public key.
You will have a **SSH Key Id** to use with your local config file.

Then we need couple of config more
```
cd ~/.ssh
touch config
chmod 600 config
```

And then edit the config file and paste the following and replace your **SSH Key Id** 
```
Host git-codecommit.*.amazonaws.com
  User [YOUR_SSH_KEY_ID_FROM_IAM]
  IdentityFile ~/.ssh/aws_rsa
```

# Now you can connect to repositories.
