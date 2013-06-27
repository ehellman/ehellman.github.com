---
layout: post
title: "Heroku Permission denied (publickey)"
date: 2013-06-27 19:08
comments: true
categories:
- heroku
- ssh
- ruby on rails
- rubygems
---
I was presented with this today when I tried to push my app to Heroku.
<!-- more -->
```
$ git push heroku master
The authenticity of host 'heroku.com (X.X.X.X)' can't be established.
RSA key fingerprint is X:X:X:X:X:X:X:X:X:X.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added 'heroku.com,X.X.X.X' (RSA) to the list of known hosts.
Identity added: /Users/username/.ssh/id_rsa (/Users/username/.ssh/id_rsa)
Permission denied (publickey).
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
```

This happens when your ssh-keys aren't uploaded to Heroku. The solution is:
```
$ heroku keys:add ~/.ssh/id_rsa.pub
Uploading SSH public key /Users/username/.ssh/id_rsa.pub... done
```