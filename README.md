caddy-hhvm
===
The swankiest way to serve PHP since sliced bread.

## Requirements

* A newer version of `docker`.
* A newer version of `docker-compose` than you can `apt-get install` on Ubuntu 16.04 LTS.

## Usage
You may need to build the images the first time you run:

    docker-compose up

You could volume mount config files, or continue to inject it at build time with this workflow:

    docker-compose rm -f && docker-compose build --force-rm && docker-compose up

## Test
_NOTE:_ `docker-config.yml` defaults will attempt to bind to your Docker hosts public network iterface on ports 80 and 443.

Open a browser to [http://localhost](http://localhost) to try it out.

## Issues

* hhvm takes a while to exit on <cntrl-c>.
* No hhvm in Alpine Linux yet.
* You need custom builds of Caddy to support all the sweet Addons.
* Use `tls self_signed` during debugging so as not to exceed on-demand ACME CA rate limits when using `tls you@yourhost.com`.

## References
* [Example Config](https://github.com/caddyserver/examples/tree/master/hhvm)
* [DenBeke Blog](https://denbeke.be/blog/servers/two-months-ago-i-started-to-serve-the-web-like-its-2016-and-im-still-loving-caddy-migrating-from-nginx-to-caddy-server/)
