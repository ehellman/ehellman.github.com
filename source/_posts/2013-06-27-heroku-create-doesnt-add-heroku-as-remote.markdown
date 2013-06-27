---
layout: post
title: "'heroku create' doesn't add heroku as remote"
date: 2013-06-27 19:06
comments: true
categories:
- heroku
- ruby on rails
- rubygems
---
```
$ git push heroku master
fatal: 'heroku' does not appear to be a git repository
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
```

This problem occurs because you don't have heroku listed as a remote, to add it, execute the following:
<!-- more -->
```
$ git remote add heroku git@heroku.com:application-name.git
```

Replacing 'application-name' with the actual name of your application. Now the push should succeed:
```
$ git push heroku master
Counting objects: 63, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (49/49), done.
Writing objects: 100% (63/63), 25.92 KiB, done.
Total 63 (delta 2), reused 0 (delta 0)


-----> Ruby/Rails app detected


. . .
```