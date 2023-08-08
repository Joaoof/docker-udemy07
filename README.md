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

