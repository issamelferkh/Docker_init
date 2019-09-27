### Before we get started
- 01: docker-machine create --driver virtualbox --virtualbox-memory "2048" Char
- 02: docker-machine ip Char
- 03: eval $(docker-machine env Char)
- 04: docker pull hello-world
- 05: docker run hello-world
- 06: docker run -d -p 5000:80 --name overlord --restart=always nginx
	* run -d => Launch as a background task
	* --name overlord => It should be named "overlord"
	* --restart=always => be able to restart on its own
	* -p 5000:80 => its 80 port attached to the 5000 port of Char
check that your container functions by visiting http://<ip-de-char>:5000


### Docker CMD
- docker --version
- docker-machine --version
- docekr-compose --version
- docker info 
- docker images -> list images (containers)
- docker volume ls -> list volumes created in VM
- To see how to connect your Docker Client to the Docker Engine running on this virtual machine, run: ```docker-machine env Char```


