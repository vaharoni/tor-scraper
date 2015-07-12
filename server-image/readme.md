Docker Tor Privoxy
==================

Merged https://github.com/eg5846/tor-docker and https://github.com/sherzberg/docker-tor-http-proxy 

Simple single container that sets up a tor proxy via socks and an http proxy to that tor relay.

Run
-----

```bash
$ docker run -P --name tor -h tor vaharoni/torprivoxy
$ docker run -P -e TOR_EXITNODES={ca} --name tor -h tor vaharoni/torprivoxy
```

Run on daemon
------

```bash
$ docker run -d -P --name tor -h tor vaharoni/torprivoxy
$ docker run -d -P -e TOR_EXITNODES={ca} --name tor -h tor vaharoni/torprivoxy
```

Inspect tor docker container
------

```bash
# Show stdout
sudo docker logs tor

# Run bash inside container
sudo docker exec -it tor /bin/bash
cat /var/log/tor/notice.log
exit

# Access logfile on volume directly
docker run --rm -t --volumes-from tor ubuntu:14.04 cat /var/log/tor/notice.log
```