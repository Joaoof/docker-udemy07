# <a href="https://imasters.com.br/desenvolvimento/vamos-conhecer-o-docker-swarm">Iniciando no docker Swarm</a>

* <p>docker <strong>init</strong> swarm --advertise-addr (ip) --> node 1</p>
`obs: em alguns casos necessários, o "--advertise-addr (ip)" deve ser inserido`

* <p>docker swarm join --token SWMTKN-1-27n7zv6rtp8e07vrnmetv29ypv3y3a3hl03d6zrqkpgropj699-79qnbmcgngs36bdde2rmg5kgy 192.168.0.28:2377 --> distribuir isso nas outras maquinas (ex; node2, node3, e vice versa...)</p>

# replicando maquinas: 

* docker service create --name (nome do service) --replicas (numero de maquinas) -p 80:80

no exemplo desse projeto, ficaria assim: 

* docker service create --name nginxreplicas --replicas 3 -p 80:80

# Token para Join

* docker swarm join-token manager

# Rodando Compose com Swarm

* sudo docker stack deploy -c docker-compose.yml nginx_swarm

# Escalando nossa aplicação (em 3 maquinas)

 * docker service scale nginx_swarm_web=3

# Parar de receber Tasks em um Node

* docker node update --availability drain (id do node ls )

![comando na pratica](<Captura de tela 2023-08-08 171949-1.png>)

# Atualizando uma imagem no Swarm

* sudo docker service update --image nginx:1.18 pdq

![nsnsn](<Captura de tela 2023-08-08 174013.png>)

# Criando redes para serviços do Swarm

* docker network create --driver overlay swarm 

# Conectando serviço a uma rede já existente 

* docker service update --network-add (rede) (ID)
`para adicionar o network, é necessário que você liste as networks.` ***Como fazer isso?*** 

* docker network ls

# Conclusão......Swarm

# <a href="https://www.supero.com.br/blog/kubernetes-vs-docker/">Iniciando Docker no Kubernetes</a>

* Control Plane: Gerenciamento dos controles de processos do Nodes
* Nodes: Maquinas que são gerenciadas pelo Control Plane
* Deployment: A execução de uma imagem/projeto em um Pod
* Pod: um ou mais containers que estão em um Node
* Services: serviços que expõe os Pods ao mundo externo
* kubectl: Cliente de linha de comando para o Kubernetes

# Iniciando o Minikube

* minikube start --driver=`<DRIVER>`  

# Parando Minikube

* minikube stop

# Acessando a dashboard do Kubernetes

* minikube dashboard 

`caso eu queira obter a url do minikube dashboard --url`

* minibuke dashboard --url
