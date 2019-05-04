# Space Heater 2.0

Plex, Tautulli, Radarr, Sonarr, Nzbget

# Installation

1. Install Docker
1. Install Docker Compose
1. Edit `docker-compose.yml`:
   - Replace all instances of `/drobo/` in each of the `volumes` section with
     the location of your media.
   - Append your plex claim token to the line with `PLEX_CLAIM=`
   - Probably more that I can't think of...
1. Run `docker-compose up -d`

# Usage

All containers are accessible through the Nginx proxy. You may wish to update
the `VIRTUAL_HOST` environment vars of each container with your own name.

Default hostnames:

- http://tautulli.space-heater/
- http://nzbget.space-heater/
- http://sonarr.space-heater/
- http://radarr.space-heater/

If your network uses `dnsmasq`, you can add these lines to your configuration
and the URLs above will light up (change `10.0.0.2` to your host's IP address).

```
rebind-domain-ok=/plex.direct/
address=/space-heater/10.0.0.2
```

# Contributing

Please feel free to help me out by opening an issue or creating a Pull Request.
This is just a personal pet project so there won't be a lot of structure to it.
