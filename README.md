# Meetup Ethereum Sevilla: Swarm.
![EthSvq](./images/EthSvq.jpg)
Repositorio para el [meetup](https://www.meetup.com/es-ES/Ethereum-Meetup-Sevilla/events/256802370/) de Ξthereum Sevilla sobre Swarm que se realizará el Jueves 6 de Diciembre en la [Colmena](https://www.coworkingcolmena.com/).


# Introducción
![Swarm](./images/swarm.png)

[Swarm](https://swarm-gateways.net/bzz:/theswarm.eth/) es una plataforma de almacenamiento distribuido y servicio de difusión de contenidos, un servicio de capa base nativa de la pila Ξthereum [web3](https://web3js.readthedocs.io/en/1.0/getting-started.html). El objetivo principal de Swarm es proporcionar un almacenamiento descentralizado y redundante para el código Đapp y los datos, así como para la cadena de bloques y los datos de estado. Swarm también se propone suministrar varios servicios de capa base para la web3, incluyendo mensajería nodo a nodo, streaming de medios, servicios de bases de datos descentralizados e infraestructura escalable de canales estatales para economías de servicios descentralizados.

## Diseñado para Ξthereum
Desde la perspectiva del usuario final, Swarm no es tan diferente de la World Wide Web. En segundo plano, la diferencia es que el contenido se aloja en una red de almacenamiento peer-to-peer en lugar de en servidores individuales. Esta red peer-to-peer es autosuficiente gracias a un sistema de incentivos integrado que utiliza la contabilidad peer-to-peer y permite el intercambio de recursos para el pago. Swarm está diseñado para integrarse perfectamente con la capa de red multiprotocolo devp2p de Ξthereum, así como con la blockchain de Ξthereum para la resolución de nombres de dominio, pagos de servicios y seguros de disponibilidad de contenido.


# Características
## ![Fault Tolerant](./images/faultTolerant.png) Tolerancia a fallos 
Almacenamiento redundante: la replicación garantiza la disponibilidad de los datos, incluso en caso de producirse un fallo en los nodos o una pérdida de datos.

## ![Censorship Resistant](./images/censorshipResistant.png) Resistente a la censura
Los sitios no pueden ser _"retirados"_: los datos se almacenan en toda la red sin nodos centrales vulnerables.

## ![DDoS Resistant](./images/DDoSResistant.png) Resistente a ataques DDoS
La red [peer-to-peer o p2p](https://es.wikipedia.org/wiki/Peer-to-peer) totalmente descentralizada es más resistente contra ataques [DDoS](https://es.wikipedia.org/wiki/Ataque_de_denegaci%C3%B3n_de_servicio) que cualquier otro sistema centralizado.

## ![Zero Downtime](./images/zeroDowntime.png) Tiempo de inactividad cero
La redundancia garantiza que la red siga entregando datos incluso cuando los nodos individuales están fuera de línea.

## ![Self Sustaining](./images/selfSustaining.png) Autosuficiente
El sistema de incentivos incorporado garantiza la viabilidad económica de la red.


# Instalación

## · Usando la imagen preparada de virtualbox
Hemos preparado una imagen para importarla en virtualBox con todo lo necesario para empezar con Swarm, podéis encontrarla a través del siguiente [enlace](https://www.coworkingcolmena.com/vm/swarmworkshop.zip)

> Es una imagen de `43GB` pero está comprimida y pesa `4.3GB`

Las credenciales de la máquina virtual son:
```
User:user
Passwd:user
```

En el `/home/` he creado una carpeta llamada  `/swarm` con un HTML muy básico para poder hacer una prueba de nuestra primera web en Swarm

En `/home/user/Documentos/` hay un archivo llamado `infoAccountSwarm`, en él podeis encontrar la wallet que se ha creado, información sobre la misma y sobre el nodo

_En el `.bash_history` podéis observar todos los comandos que se han utilizado en el proceso de instalación. De igual manera `history` también muestra los comandos introducidos durante el proceso de instalación_

## · Si hacemos una instalación desde cero
### Dependencias
Necesitamos tener [Go](https://golang.org/) y [Git](http://git.org/) instalado.


# Nuestra primera web
>Por comodidad usaremos [tmux](https://github.com/tmux/tmux/wiki) para disponer de más de una terminal en la misma ventana. Se pueden seguir estos pasos simplemente abriendo dos terminales o usando cualquier otra alternativa que prefiera el usuario ([terminator](https://launchpad.net/terminator), por ejemplo)

>Para más información sobre `tmux` [aquí](https://man.openbsd.org/OpenBSD-current/man1/tmux.1) y [aquí](https://raw.githubusercontent.com/tmux/tmux/master/README).

- Abrimos una terminal y creamos una sesion de tmux con tres terminales 
```
$ tmux new-session \; split-window -h \; split-window -v
```
> Para conocer más comandos y atajos disponibles en tmux podéis visitar la siguiente [web](https://tmuxcheatsheet.com/)
- En una de las divisiones ejecutamos el cliente ligero (_en este caso usamos Ropsten_):
```
$ geth --testnet --syncmode=light
```
- En otra división conectamos nuestro nodo con la cuenta generada:
```
$ swarm -bzzaccount 5ba32decbbf981812dcec51f0472b34b3ed24c63
```
>passphrase: ColmenaUser!
- En la tercera división creamos el hash de nuestro HTML básico:
```
$ swarm up /home/user/swarm/index.html
```
>Este nos devuelve (recordad que el hash puede variar): `c5f4639a3fe728642b70c199df373c732dd81cd49b88573788712bf70ca204b6`

- Abrimos el navegador en localhost y añadimos el hash generado anteriormente:
[http://localhost:8500/bzz:/c5f4639a3fe728642b70c199df373c732dd81cd49b88573788712bf70ca204b6](http://localhost:8500/bzz:/c5f4639a3fe728642b70c199df373c732dd81cd49b88573788712bf70ca204b6)

_Enhorabuena!! con estos pasos ya tendríamos nuestro HTML básico en Swarm!_












## Enlaces de interés:
- [Página principal.](https://swarm-gateways.net/bzz:/theswarm.eth/#)
- [Repositorio oficial.](https://github.com/ethersphere)
- [Issues.](https://github.com/ethersphere/go-ethereum/issues)
- [Código fuente.](https://github.com/ethereum/go-ethereum)
- [Documentación.](https://swarm-guide.readthedocs.io/en/latest/)
- [Proyectos.](https://swarm-gateways.net/bzz:/theswarm.eth/#projects)
- [Roadmap.](https://github.com/ethersphere/swarm/wiki/Roadmap)
- [Roadmap (2018).](https://github.com/orgs/ethersphere/projects/5)
- [Descargas.](https://swarm-gateways.net/bzz:/theswarm.eth/downloads/)
- [Gitter.](https://gitter.im/ethereum/swarm)
- [Reddit/r/ethswarm.](https://www.reddit.com/r/ethswarm)
- [Twitter Swarm.](https://twitter.com/ethswarm)
- [Twitter Ethersphere.](https://twitter.com/ethersphere)
- [Swarm Orange Summit 2018](https://swarm-gateways.net/bzz:/swarm-orange-summit.eth/)
- [Working groups](https://github.com/ethersphere/swarm/wiki/Working-groups)
- [Comunicado POC3 (21-Junio-2018).](https://blog.ethereum.org/2018/06/21/announcing-swarm-proof-of-concept-release-3/)
- [Swarm public gateway.](https://swarm-gateways.net/)
- [Swarm Đapps.](https://swarm-gateways.net/bzz:/swarmapps.eth/)
- [Código fuente Đapps.](https://github.com/ethersphere/Swarm-dapps)
- [Orange papers (swap, swear and swindle)](https://swarm-gateways.net/bzz:/theswarm.eth/ethersphere/orange-papers/1)
- [Podcast.](https://oktahedron.diskordia.org/?podcast=oh003-Swarm)
- [Videos](https://swarm-guide.readthedocs.io/en/latest/resources.html#videos)
- [Swarm team](https://blog.ethereum.org/img/2018/06/swarm_team_2018.jpg)