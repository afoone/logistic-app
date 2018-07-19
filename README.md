## ¿Qué es una aplicación blockchain?

En una aplicación blockchain, el blockchain almacenará el estado del sistema, además del registro inmutable de las transacciones que crearon ese estado. Se usará una aplicación cliente para enviar transacciones a la cadena de bloques. Los smart contracts codificará la lógica de negocio.

Las aplicaciones usan API para ejecutar los smart contracts. En Hyperledger Fabric, por ejemplo, estos contratos inteligentes se llaman chaincode. Estos contratos se alojan en la red y se identifican por nombre y versión. Las API son accesibles normalmente con un kit de desarrollo de software o SDK.

En este ejercicio, veremos cómo un usuario puede interactuar con una red a través de una aplicación que permite a los usuarios consultar y actualizar un ledger. Nuestra aplicación maneja la interfaz de usuario y envía transacciones a la red, que luego llama a chaincodes (smart contracts en hyperledger fabric). Actualmente, Fabric tiene tres opciones para los desarrolladores: un Node SDK, Java SDK y una interfaz de línea de comandos o CLI.

Usaremos el SDK de Node.js de Fabric, que hace que sea fácil usar las API para interactuar con la cadena de bloques Hyperledger Fabric. Leer o escribir el libro mayor se conoce como una propuesta (proposal). Esta propuesta es construida por nuestra aplicación a través del SDK, y luego enviada a un nodo de blockchain. El nodo se comunicará con su contenedor chaincode específico de la aplicación y éste ejecutará la transacción.  Si no hay problemas, respaldará la transacción y la enviará a nuestra aplicación. Nuestra aplicación, a través del SDK, enviará la propuesta endosada al servicio de ordenación.
La orden incluirá muchas propuestas de toda la red en un bloque, que luego se transmitirá a los pares en la red.
Finalmente, el nodo validará el bloque y lo escribirá en su ledger.

## Instalando y ejecutando la aplicación

Para ejecutar la aplicación necesitarás tener instalado docker en el sistema, así como node.js y para seguir las instrucciones el node package manager `npm`

Para ejecutar la aplicación clonar:

```sh
git clone https://github.com/afoone/logistic-app.git
```

tras esto entramos en logistics-app y ejecutamos:

```sh
cd logistics-app/
./startFabric.sh
```

Si hacemos `docker ps` deberíamos ver más o menos esto:

```sh
CONTAINER ID        IMAGE                                                                                                      COMMAND                  CREATED             STATUS              PORTS                                            NAMES
96a4a49e4a41        dev-peer0.org1.example.com-tuna-app-1.0-b58eb592ed6ced10f52cc063bda0c303a4272089a3f9a99000d921f94b9bae9b   "chaincode -peer.add…"   5 minutes ago       Up 5 minutes                                                         dev-peer0.org1.example.com-tuna-app-1.0
b48876dc9008        hyperledger/fabric-tools                                                                                   "/bin/bash"              6 minutes ago       Up 6 minutes                                                         cli
603d1a276909        hyperledger/fabric-peer                                                                                    "peer node start"        7 minutes ago       Up 7 minutes        0.0.0.0:7051->7051/tcp, 0.0.0.0:7053->7053/tcp   peer0.org1.example.com
047e4419be10        hyperledger/fabric-ca                                                                                      "sh -c 'fabric-ca-se…"   7 minutes ago       Up 7 minutes        0.0.0.0:7054->7054/tcp                           ca.example.com
7674e8addb15        hyperledger/fabric-orderer                                                                                 "orderer"                7 minutes ago       Up 7 minutes        0.0.0.0:7050->7050/tcp                           orderer.example.com
a1295ab28b9b        hyperledger/fabric-couchdb                                                                                 "tini -- /docker-ent…"   7 minutes ago       Up 7 minutes        4369/tcp, 9100/tcp, 0.0.0.0:5984->5984/tcp       couchdb
```

Ahora vamos a instalar las dependencias y arrancar node.js:

```
npm install
npm start
```






---
This code is based on code written by the Hyperledger Fabric community. Source code can be found here: (https://github.com/hyperledger/fabric-samples). 
