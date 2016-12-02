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
copy certbotRenew to /usr/local/sbin/
$ chmod +x certbotRenew

Run manualy to install git and pull down fresh version of certbot-auto to /opt/certbot/
$ certbotRenew

Add your first certificate
$ certbot-auto certonly --webroot -w <docRoot> -d <domain> [-d domainalias>]
Update webserver config, your own way, to include certificates.

Add to daily cron

## tested
on ubuntu 14.04 and 16.04 and should work on most debian based systems.
