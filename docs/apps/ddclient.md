# Ddclient

[DDclient](https://sourceforge.net/p/ddclient/wiki/Home/) is a Perl client used to update dynamic DNS entries for accounts on a Dynamic DNS Network Service Provider. It was originally written by Paul Burry and is now mostly by wimpunk. It has the capability to update more than just dyndns and it can fetch your WAN-ipaddress in a few different ways.

The GIT Repository for Ddclient is located at [https://github.com/linuxserver/docker-ddclient](https://github.com/linuxserver/docker-ddclient).

## Ddclient Install

Ddclient is a Perl client used to update dynamic DNS entries for accounts on Dynamic DNS Network Service Provider. It was originally written by Paul Burry and is now mostly by wimpunk. It has the capability to update more than just dyndns and it can fetch your WAN-ipaddress in a few different ways.

- App: [[Website](https://docs.linuxserver.io/images/docker-ddclient)] [[App Source](https://github.com/linuxserver/docker-ddclient)]
- Docker Image: [[Docker Hub](https://hub.docker.com/)] [[Image Source](https://hub.docker.com/r/linuxserver/ddclient)]

---


Edit the included config to uncomment this line:

```ini
use=web, web=checkip.dyndns.org/, web-skip='IP Address' # found after IP Address
```

Then find your service of choice in the file and fill out the info as described. CloudFlare is recommended.
