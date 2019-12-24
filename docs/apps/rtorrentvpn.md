# rTorrentVPN

rTorrent is a quick and efficient BitTorrent client that uses, and is in development alongside, the libTorrent (not to be confused with libtorrent-rasterbar) library. It is written in C++ and uses the ncurses programming library, which means it uses a text user interface. When combined with a terminal multiplexer (e.g. GNU Screen or Tmux) and Secure Shell, it becomes a convenient remote BitTorrent client. This Docker image includes the popular ruTorrent web frontend to rTorrent for ease of use, as well as OpenVPN to ensure a secure and private connection to the Internet, including use of iptables to prevent IP leakage when the tunnel is down. Privoxy is also included to allow unfiltered access to index sites, to use Privoxy please point your application at http://:8118.

- App: [[Website](http://apps-website)] [[App Source](https://github.com/binhex/arch-rtorrentvpn)]
- Docker Image: [[Docker Hub](https://hub.docker.com/)] [[Image Source](https://hub.docker.com/r/binhex/arch-rtorrentvpn/dockerfile)]

The support forum for rTorrentVPN is located at [https://forums.unraid.net/topic/46127-support-binhex-rtorrentvpn/](https://forums.unraid.net/topic/46127-support-binhex-rtorrentvpn/).

The GIT Repository for rTorrentVPN is located at [https://github.com/binhex/arch-rtorrentvpn](https://github.com/binhex/arch-rtorrentvpn).

## rTorrentVPN WebUI Access

If you're attempting to get access to the rTorrentVPN WebUI remotely outside of your home network, you are going to have to do this through a Proxy using LetsEncrypt. Full details and steps are outlined here [VPN Information](https://dockstarter.com/advanced/vpn-info/).

The sample proxy configuration files found in `.docker/config/letsencrypt/nginx/proxy-confs/` will need to be modified and as usual, have the .sample removed from the filename.

You will need to edit the appropriate proxy `.conf`. Enter either `sudo nano rutorrent.subfolder.conf` or `sudo nano rutorrent.subdomain.conf` depending on your configuration desires and change the below lines. NOTE: There will be multiple lines that need to be changed.

Original

```nginx
   set $upstream_rutorrent rutorrent;
   proxy_pass http://$upstream_rutorrent:80;
```

Modified

```nginx
   set $upstream_rutorrent rtorrentvpn;
   proxy_pass http://$upstream_rutorrent:9080;
```

Save the file out and then restart your containers with a `ds -c` command.
