
  
  

# Assignment: DNS Round-Robin Test

  

  

* Create a new virtual network (default bridge driver)
* Create two containers `elasticsearch:2` image
* Research and use `-network-alias search` when creating them to give them an additional DNS name to respond to
* Run `alpine nslookup search` with `--net` to see the two containers list for the same DNS name
* Run `centos  curl -s search:9200` with `--net` multiple times until you see both "name" fields show
*   

  

## Answer

```

# create network
docker  network create test

# start elasticsearch containers
docker run -d --name elastic1 --net test --network-alias search elasticsearch:2
docker run -d --name elastic2 --net test --network-alias search elasticsearch:2

#  Check in alpine 
docker run --rm --net test alpine nslookup search

# Check in centos
docker run --rm --net test centos  curl -s search:9200

```