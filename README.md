# Meetup Ethereum Sevilla: Swarm.
![EthSvq](./images/EthSvq.jpg)
Repositorio para el meetup de Ξthereum Sevilla sobre Swarm que se realizará el Jueves 6 de Noviembre en la [Colmena](https://www.coworkingcolmena.com/).


# Introducción:
![Swarm](./images/swarm.png)

[Swarm](https://swarm-gateways.net/bzz:/theswarm.eth/) es una plataforma de almacenamiento distribuido y servicio de difusión de contenidos, un servicio de capa base nativa de la pila Ξthereum [web3](https://web3js.readthedocs.io/en/1.0/getting-started.html). El objetivo principal de Swarm es proporcionar un almacenamiento descentralizado y redundante para el código Đapp y los datos, así como para la cadena de bloques y los datos de estado. Swarm también se propone suministrar varios servicios de capa base para la web3, incluyendo mensajería nodo a nodo, streaming de medios, servicios de bases de datos descentralizados e infraestructura escalable de canales estatales para economías de servicios descentralizados.

## Diseñado para Ξthereum:
Desde la perspectiva del usuario final, Swarm no es tan diferente de la World Wide Web. En segundo plano, la diferencia es que el contenido se aloja en una red de almacenamiento peer-to-peer en lugar de en servidores individuales. Esta red peer-to-peer es autosuficiente gracias a un sistema de incentivos integrado que utiliza la contabilidad peer-to-peer y permite el intercambio de recursos para el pago. Swarm está diseñado para integrarse perfectamente con la capa de red multiprotocolo devp2p de Ξthereum, así como con la blockchain de Ξthereum para la resolución de nombres de dominio, pagos de servicios y seguros de disponibilidad de contenido.


# Características:
![Fault Tolerant](./images/faultTolerant.png)
## Tolerancia a fallos
Almacenamiento redundante: la replicación garantiza la disponibilidad de los datos, incluso en caso de producirse un fallo en los nodos o una pérdida de datos.

![Censorship Resistant](./images/censorshipResistant.png)
## Resistente a la censura:
Los sitios no pueden ser _"retirados"_: los datos se almacenan en toda la red sin nodos centrales vulnerables.

![DDoS Resistant](./images/DDoSResistant.png)
## Resistente a ataques DDoS:
La red [peer-to-peer o p2p](https://es.wikipedia.org/wiki/Peer-to-peer) totalmente descentralizada es más resistente contra ataques [DDoS](https://es.wikipedia.org/wiki/Ataque_de_denegaci%C3%B3n_de_servicio) que cualquier otro sistema centralizado.

![Zero Downtime](./images/zeroDowntime.png)
## Tiempo de inactividad cero:
La redundancia garantiza que la red siga entregando datos incluso cuando los nodos individuales están fuera de línea.

![Self Sustaining](./images/selfSustaining.png)
## Autosuficiente:
El sistema de incentivos incorporado garantiza la viabilidad económica de la red.


# Instalación:
_Hemos preparado una imagen para importarla en virtualBox con todo lo necesario para empezar con Swarm, podéis encontrarla en la [web](https://www.coworkingcolmena.com/vm/) de la Colmena, es una imagen de `43GB` pero está comprimida y pesa `4.3GB`. Las credenciales de la máquina virtual son:_
```
User:user
Passwd:user
```
_En el `.bash_history` podéis observar todos los comandos que se han utilizado en el proceso de instalación, de igual manera `history` también muestra los comandos introducidos durante el proceso de instalación_

_En el `/home/` he creado una carpeta llamada  `/swarm` con un HTML muy básico para poder hacer una prueba de nuestra primera web en Swarm_

_En `/home/Documentos/` hay un archivo llamado `infoAccountSwarm`, en el podeis encontrar la wallet que se ha creado, e información sobre la misma y sobre el nodo_

# Si importamos la imagen de virtualbox:
- Abrimos una terminal y creamos una sesión nueva con [tmux](https://github.com/tmux/tmux/wiki):
```
$ tmux
```
- Esa sesión de tmux la dividimos en dos pulsando ` Ctrl + b + " ` (para más información sobre `tmux` [aquí](https://man.openbsd.org/OpenBSD-current/man1/tmux.1) y [aquí](https://raw.githubusercontent.com/tmux/tmux/master/README)).
- En una de las divisiones ejecutamos el cliente ligero (_en este caso usamos Ropsten_):
```
$ geth --testnet --syncomde=light
```
- En la otra división conectamos nuestro nodo con la cuenta generada:
```
$ swarm -bzzaccount 50385f84ca4fa0d2934fa5a3e00ccb165683f1b9
```
- Abrimos una nueva terminal y creamos el hash de nuestro HTML básico:
```
$ swarm up /home/user/swarm/index.html
```
^Este nos devuelve (recordad que el hash puede variar): `fe1c81c0a0462d112502c57994191800b03c35303ab3be7f65119d0d28aaf45e`

- Abrimos el navegador en localhost y añadimos el hash generado anteriormente:
[localhost:8500/bzz:/fe1c81c0a0462d112502c57994191800b03c35303ab3be7f65119d0d28aaf45e](localhost:8500/bzz:/fe1c81c0a0462d112502c57994191800b03c35303ab3be7f65119d0d28aaf45e)

_Enhorabuena!! con estos pasos ya tendríamos nuestro HTML básico en Swarm!_


# Si hacemos una instalación desde cero
## Dependencias: 
Necesitamos tener [Go](https://golang.org/) y [Git](http://git.org/) instalado.














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