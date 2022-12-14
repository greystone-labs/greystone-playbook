# Containerization

Containerization is tightly coupled with [12factor](12factor.md) and [governance](governance.md)

Productionization requirements dictate that services MUST be containerized prior to release and SHOULD be a part of the development lifecycle

Benefits of containerization, include 
* Parity between test/development/staging/production
* Consistent deployments (rolling) and horizontal scaling
* Agility
* Portability (multi-cloud, multi-service)
* 1-click development enviroment that mirrors production
* Continuous Deployment and Testing ensures code promoted includes libs, changes, etc.

Specifically, 12factor requirements are parity. 

We talk a lot about parity, similarly to physics as symmetry property of processes, as it converns the environments that we deal with, namely Test, Development, Staging, Production. To guarantee that what we are building, testing, and deploying exact replicias (checksums) of code base, libraries, etc. The discerning feature is simply configuration. 

Learn more by reading about how [OCI](https://opencontainers.org/about/overview/) and governance intersect.

## OCI Containers - Podman vs Docker

 ### [Podman](https://docs.podman.io/en/latest/index.html])

https://docs.podman.io/en/latest/index.html

https://podman.io/getting-started/installation.html

https://github.com/containers/podman-compose

https://podman-desktop.io/docs/Installation/windows-install
suggest the (flatpak)[https://www.flatpak.org/] setup if your OS supports it. WSLv2?

https://phoenixnap.com/kb/podman-tutorial


## Windows and WSLv2

DO NOT JUST COPY AND PASTE

Setting Up Podman in Ubuntu WSL (https://podman.io/getting-started/installation)

DO NOT JUST COPY AND PASTE

1. sudo apt update
2. sudo apt-get -y upgrade
3. sudo apt install podman
  - If step #3 fails run the following to install new ubuntu repositories:
  3a. echo "deb https://download.opensuse.org/repositories/devel:/kubic:/libcontainers:/stable/xUbuntu_20.04/ /" | \nsudo tee /etc/apt/sources.list.d/devel:kubic:libcontainers:stable.list
  3b. curl -L "https://download.opensuse.org/repositories/devel:/kubic:\\n/libcontainers:/stable/xUbuntu_20.04/Release.key" | sudo apt-key add -
  3c. re-run steps 1 - 3

4. cd <directory-where-you-save-third-part-binaries>
5. curl -o ./podman-compose https://raw.githubusercontent.com/containers/podman-compose/devel/podman_compose.py
6. chmod 666 ./podman-compose
7. sudo ln -s ${PWD}/podman-compose /usr/local/bin/podman-compose


