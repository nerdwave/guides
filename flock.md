# flock 🕊
## Ops & Orchestration 📡

### Docker Machine 💻
- - - -
* Use **docker-machine** to manage dev, staging, QA, prod. cluster. Necessary commands: (docker-machine -> dm)
> **dm active** -> shows active machine  
> **dm create** -> create new machines, local or cloud  
> **dm scp** -> copy files to and from  
> **dm ssh dev -L 8000:localhost:8080** -> forward port 8000 from dev to localhost:8080  
> **dm upgrade <machine>** -> upgrades Docker Engine  
	
### Docker Swarm 🐋🐳
- - - -
* regular Docker -> standalone container commands
* Docker Swarm -> orchestrate tasks to execute on a cluster

**swarm** - a cluster of Docker engines (nodes)
* manger nodes perform cluster management and can also work
* worker nodes execute tasks sent from manager
* to deploy to a swarm, submit a service to manager node
* services are made of tasks that carry Docker containers and commands to run in the container
* Service -> docker.compose.yml
* Task -> Dockerfile

**Initialization**
- - - -
> **docker swarm init** -> creates swarm, turns node in manager (*creates worker & manager tokens*)  
> **docker swarm join-token <manager/worker>** -> gets the swarm token to add new nodes as managers or workers  

**Services**
- - - -











