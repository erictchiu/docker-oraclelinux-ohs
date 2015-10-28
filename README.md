# huhgawz/oraclelinux-ohs

## Introduction

**NOTICE: THIS IS A WORK IN PROGRESS. THIS NOTICE WILL BE REMOVED ONCE I FEEL COMFORTABLE WITH IT. CONTRIBUTIONS ARE WELCOME.**

Dockerized `Oracle Linux` with `Oracle HTTP Server` (`OHS`).

## Installation

1. Go to [Oracle Web Tier Downloads](http://www.oracle.com/technetwork/middleware/webtier/downloads/index.html)
2. Click the **Accept License Agreement** radio button
3. In the **Web Tier 11gR1 - 11.1.x.x** combo box, select the **Linux 64-bit** option
4. Click the **Download File** button
6. Clone this repo: `$ git clone https://github.com/huhgawz/docker-oraclelinux-ohs.git && cd docker-oraclelinux-ohs`
7. Move downloded zip file to the cloned repo: `$ mv ~/Downloads/ofm_webtier_linux_11.1.x.x.x_64_disk1_1of1.zip  .`
8. Update the value of the [OHS_VERSION](https://github.com/huhgawz/docker-oraclelinux-ohs/blob/master/Dockerfile#L15) environment variable accordingly: `$ vi Dockerfile`
9. Build the image: `$ docker build --rm=true --tag=oraclelinux-ohs .`
10. Run a container: `$ docker run -it -p 9000:7777 --name ohs <IMAGE-ID> /bin/bash`
11. In the docker container, start `OHS`: `$ ./oracle/Middleware/Oracle_WT1/opmn/bin/opmnctl startall` 

## TODO

- Get `OHS` installation zip file via `wget` or `curl`
- Start `OHS` when the image is run
- Expose volume for configuration files

## References

- [Oracle HTTP Server](http://www.oracle.com/technetwork/middleware/webtier/overview/index.html#OHS)
- [Oracle Web Tier Downloads](http://www.oracle.com/technetwork/middleware/webtier/downloads/index.html)
- [Oracle Fusion Middleware Installation Guide for Oracle Web Tier](https://docs.oracle.com/middleware/11119/webtier/install-ohs/toc.htm)
