# flock 🕊
## 1. Docker Concepts 🐋
### Running a Container
* containers can run in foreground or **detached** (in background)
* can expose container ports to allow internal/external communication

> **docker run -d -p <>:<> <container_name/id> [command]** -> run container   
> **docker attach <container_name/id>** -> connect to a running container  
> **docker run -it <container_name/id>** -> open a term on a container   
> **docker top <container_name/id>** -> show container processes  
> **docker logs -f <container_name/id>** -> see console output   
> **docker stop <container_name/id>** -> stop container  
> **docker rm <container_name/id>** -> remove a container  

### Building Images

* images can be built from Dockerfiles or pulled and layered on top of
* to build an image from an existing base image:

1. Pull Base Image
2. Open Terminal into Container
3. Add/Install Necessary Tools/Depedencies/Languages etc.
4. **docker commit** and exit

### Linking Containers & Networking

* docker run -d -p <host_port>:<container port> [name, opts]
	* can bind to localhost, port, ip addresses etc.

Network Types
* Bridge:
	* Docker Host/Machine Wide
	* Can be extended to expose some containers in network
* User-Defined Bridge:
	* Extension of default bridge network
* Overlay
	* Spreads across the swarm (many nodes)
	* Can Have Services Attached for Interservice Comms.
	* use (`nslookup` , `dig`, and `ping`) to test connection


> **docker network ls** -> lists networks  

from inside container:
> **nslookup <tasks. ~service-name~ >** ->    






## 2. Ops & Orchestration 📡

### Docker Machine 💻
- - - -
* Use **docker-machine** to manage dev, staging, QA, prod. cluster. Necessary commands: (docker-machine -> dm)
> **dm active** -> shows active machine  
> **dm create** -> create new machines, local or cloud  
> **dm scp** -> copy files to and from  
> **dm ssh dev -L 8000:localhost:8080** -> forward port 8000 from dev to localhost:8080  
> **dm upgrade <machine>** -> upgrades Docker Engine  
	
### Docker Swarm 🐋🐳🐟
- - - -
* regular Docker -> standalone container commands
* Docker Swarm -> orchestrate tasks to execute on a cluster

##### swarm - a cluster of Docker engines (nodes)
* manger nodes perform cluster management and can also work
* worker nodes execute tasks sent from manager
* to deploy to a swarm, submit a service to manager node
* services are made of tasks that carry Docker containers and commands to run in the container
* Service -> docker.compose.yml
* Task -> Dockerfile

#### Initialization
- - - -
> **docker swarm init** -> creates swarm, turns node in manager (*creates worker & manager tokens*)  
> **docker swarm join-token <manager/worker>** -> gets the swarm token to add new nodes as managers or workers  

#### Services
- - - -
* a **bind-mount** makes file/dir on machine available to container (read only or read-write) *sharing files*
* a **named volume** decouples 










