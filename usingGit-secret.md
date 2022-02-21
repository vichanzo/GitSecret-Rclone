
Install git-secret (Alpine Linux)
```
wget https://gitsecret.jfrog.io/artifactory/git-secret-apk/all/main/x86_64/git-secret-0.
apk add --allow-untrusted git-secret-0.4.0.apk
```

Clone this repo
```
git clone https://github.com/vichanzo/GitSecret-Rclone
```

Create the git-secret folder.  This will create the .gitsecret folder.
```
git secret init
```

Add a user to the git-secret keyring
```
git secret tell teammate@example.com
```
You need your collaborator to crete a gpg key-pair and send you their public key.

To add that person, import the key and add them to the git-secret repo
```
gpg --import teammate_key.txt
git secret tell teammate@example.com
```

Now add some secret files.
Create a test file called mysecret.conf
```
MySecretAPIKey= {1234567899000}
```
Add your file as a secret file, then hide the file
```
git secret add mysecret.conf
git secret hide
```

```
git add .gitsecret/
git add  mysecret.conf.secret
```

Commit the repository and push it. 
```
git commit -a -m "adding the secret file mysecret.conf.secret"
git push ##Enter your username and token
```

References:
1) https://git-secret.io/installation
2) https://dojofive.com/blog/protect-your-security-keys-using-git-secret/
