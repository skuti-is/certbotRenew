certbotRenew
============

Renew Let's Encrypt certificates with cron on debian / ubuntu

## features
- Clones fresh certbot from github.
- Checks if there are certificates to renew and exits if there is nothing to do. (quick an quiet)
- Only if certificates are due, run certbot
- Check for nginx and/or apache are installs and reload configuration
- Only report on errors

## usage
Copy certbotRenew to /usr/local/sbin/

Make it executable

Run manualy to install git and pull down fresh version of certbot-auto to /opt/certbot/
```bash
wget -qO /usr/local/sbin/certbotRenew https://raw.githubusercontent.com/skuti-is/certbotRenew/master/certbotRenew
chmod +x /usr/local/sbin/certbotRenew
certbotRenew
```

Add your first certificate
```bash
certbot certonly --webroot -w <docRoot> -d <domain> [-d domainalias>]
```

Update webserver config, your own way, to include certificates.

Add to daily cron

## tested
on ubuntu 14.04 and 16.04 and should work on most debian based systems.
