

# Assignment: CLI App Testing

  

Use different linux distributions to check curl version

* Use two different terminal windows to start bash in both **centos:7** and **ubuntu:14.04**, using **-it**
* Learn the `docker container --rm` option so you can save cleanup
* Ensure **curl** is installed and on the latest version for that distro
	* ubuntu: `apt-get update && apt-get install curl`
	* centos: `yum update curl`
* Check `curl --version`   

## Answer
* CentOS 
```
# First start the image
docker run -it centos:7 /bin/bash

# Once inside container
yum update curl -y

# Then
curl --version

# Exit and then remove the container with 
docker rm <containerID>

```

* Ubuntu 
```
# First start the image
docker run -it ubuntu:14.04 /bin/bash

# Once inside container
apt-get update -y && apt-get install -y curl

# Then
curl --version

# Exit and then remove the container with 
docker rm <containerID>

```