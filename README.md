# Iniciando no docker Swarm

* <p>docker <strong>init</strong> swarm --advertise-addr (ip) --> node 1</p>
`obs: em alguns casos necessários, o "--advertise-addr (ip)" deve ser inserido`

* <p>docker swarm join --token SWMTKN-1-27n7zv6rtp8e07vrnmetv29ypv3y3a3hl03d6zrqkpgropj699-79qnbmcgngs36bdde2rmg5kgy 192.168.0.28:2377 --> distribuir isso nas outras maquinas (ex; node2, node3, e vice versa...)</p>

# replicando maquinas: 

* docker service create --name (nome do service) --replicas (numero de maquinas) -p 80:80

no exemplo desse projeto, ficaria assim: 

* docker service create --name nginxreplicas --replicas 3 -p 80:80

# Token para Join

docker swarm join-token manager     

