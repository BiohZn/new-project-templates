[linuxserverurl]: https://linuxserver.io
[forumurl]: https://forum.linuxserver.io
[ircurl]: https://www.linuxserver.io/irc/
[podcasturl]: https://www.linuxserver.io/podcast/
[appurl]: www.example.com
[hub]: https://hub.docker.com/r/example/example/


[![linuxserver.io](https://raw.githubusercontent.com/linuxserver/docker-templates/master/linuxserver.io/img/linuxserver_medium.png?v=4&s=4000)][linuxserverurl]

The [LinuxServer.io][linuxserverurl] team brings you another image release featuring easy user mapping and based on alpine linux with s6 overlay.

# linuxserver/rutorrent

&nbsp;

Popular rtorrent client with a webui for ease of use. [Rutorrent](https://github.com/Novik/ruTorrent)

&nbsp; 

[![rutorrent](https://raw.githubusercontent.com/linuxserver/docker-templates/master/linuxserver.io/img/rutorrent.jpg)][appurl]

&nbsp;

[![](https://images.microbadger.com/badges/version/linuxserver/rutorrent.svg)](https://microbadger.com/images/linuxserver/rutorrent "Get your own version badge on microbadger.com")[![](https://images.microbadger.com/badges/image/linuxserver/rutorrent.svg)](https://microbadger.com/images/linuxserver/rutorrent "Get your own image badge on microbadger.com")[![Docker Pulls](https://img.shields.io/docker/pulls/linuxserver/rutorrent.svg)][hub][![Docker Stars](https://img.shields.io/docker/stars/linuxserver/rutorrent.svg)][hub][![Build Status](https://ci.linuxserver.io/buildStatus/icon?job=Docker-Builders/x86-64/x86-64-rutorrent)](https://ci.linuxserver.io/job/Docker-Builders/job/x86-64/job/x86-64-rutorrent/)

&nbsp;

## Support options

| Type | Address/Details | 
| :---: | --- |
| Forum | [Linuserver.io forum][forumurl] |
| IRC | freenode at `#linuxserver.io` more information at:- [IRC][ircurl]
| Podcast | Covers everything to do with getting the most from your Linux Server plus a focus on all things Docker and containerisation! [Linuxserver.io Podcast][podcasturl] |


&nbsp;

## Usage

```
docker create \
  --name=<container-name> \
  -v <path to data>:/config \
  -e PGID=<gid> -e PUID=<uid>  \
  -p 1234:1234 \
  <image-name>
```

&nbsp;

## Parameters

`The parameters are split into two halves, separated by a colon, the left hand side representing the host and the right the container side. 
For example with a port -p external:internal - what this shows is the port mapping from internal to external of the container.
So -p 8080:80 would expose port 80 from inside the container to be accessible from the host's IP on port 8080
http://192.168.x.x:8080 would show you what's running INSIDE the container on port 80.`



| Parameter | Function |
| :---: | --- |
| `-p 1234` | the port(s) |
| `-v /config` | explain what lives here |
| `-e PGID` | for GroupID, see below for explanation |
| `-e PUID` | for UserID, see below for explanation |

&nbsp;

### User / Group Identifiers

Sometimes when using volumes (`-v` flags) permissions issues can arise between the host OS and the container, we avoid this issue by allowing you to specify the user `PUID` and group `PGID`.

Ensure any volume directories on the host are owned by the same user you specify and it will "just work" &trade;.

In this instance `PUID=1001` and `PGID=1001`, to find yours use `id user` as below:

```
  $ id <dockeruser>
    uid=1001(dockeruser) gid=1001(dockergroup) groups=1001(dockergroup)
```

&nbsp; 

## Setting up the application

Insert a basic user guide here to get a n00b up and running with the software inside the container. DELETE ME

&nbsp;

## Container access and information.

| Function | Command |
| :--- | :--- |
| Shell access (live container) | `docker exec -it <container-name> /bin/bash` |
| Realtime container logs | `docker logs -f <container-name>` |
| Container version number | `docker inspect -f '{{ index .Config.Labels "build_version" }}' <container-name>` |
| Image version number |  `docker inspect -f '{{ index .Config.Labels "build_version" }}' <image-name>` |

&nbsp;

## Versions

|  Date | Changes |
| :---: | --- |
| dd.MM.yy |  Initial Release. |
