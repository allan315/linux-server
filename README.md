# Linux Server Configuration Udacity project

In order to use login Google OAuth service please add the following line to your hosts file. This is because I don't have a nameserver for my host and Google OAuth doesn't work with IP addresses.


```
C:\Windows\System32\drivers\etc\hosts
35.205.158.96 udacity.local.com
```


**SSH**
```
Host: 35.205.158.96
Port: 2200
```



sudo password `q1w2e3r4`


## Summary

Installed software:
1. Apache2
2. Apache2 WSGI module
3. PostgreSQL

Pyhton modules:
1. Flask
2. SQLAlchemy
3. oauth2client

Web server conf:


`/etc/apache2/sites-available/flask.conf` - Apache2 conf


`/var/www/catalog/flask.wsgi` - To run my pyhton code


OS changes:
1. Created users and enabled sudo: `catalog, grader`
2. Disabled root login from `PermitRootLogin no`
3. Enabled `ufw` and allowed incoming connections to port `80, 2200` and `123`
4. Disabled password login `PasswordAuthentication no`
5. Added public key for user `grader` to `.ssh/authorized_keys` for login
6. Changed ssh port to `2200`
