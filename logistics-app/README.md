## ¿Qué es una aplicación blockchain?

En una aplicación blockchain, el blockchain almacenará el estado del sistema, además del registro inmutable de las transacciones que crearon ese estado. Se usará una aplicación cliente para enviar transacciones a la cadena de bloques. Los smart contracts codificará la lógica de negocio.

Las aplicaciones usan API para ejecutar los smart contracts. En Hyperledger Fabric, por ejemplo, estos contratos inteligentes se llaman chaincode. Estos contratos se alojan en la red y se identifican por nombre y versión. Las API son accesibles normalmente con un kit de desarrollo de software o SDK.

En este ejercicio, veremos cómo un usuario puede interactuar con una red a través de una aplicación que permite a los usuarios consultar y actualizar un ledger. Nuestra aplicación maneja la interfaz de usuario y envía transacciones a la red, que luego llama a chaincodes (smart contracts en hyperledger fabric). Actualmente, Fabric tiene tres opciones para los desarrolladores: un Node SDK, Java SDK y una interfaz de línea de comandos o CLI.

Usaremos el SDK de Nodo de Fabric, que hace que sea fácil usar las API para interactuar con la cadena de bloques Hyperledger Fabric. Leer o escribir el libro mayor se conoce como una propuesta (proposal). Esta propuesta es construida por nuestra aplicación a través del SDK, y luego enviada a un nodo de blockchain. El nodo se comunicará con su contenedor chaincode específico de la aplicación y éste ejecutará la transacción.  Si no hay problemas, respaldará la transacción y la enviará a nuestra aplicación. Nuestra aplicación, a través del SDK, enviará la propuesta endosada al servicio de ordenación.
La orden incluirá muchas propuestas de toda la red en un bloque, que luego se transmitirá a los pares en la red.
Finalmente, el nodo validará el bloque y lo escribirá en su ledger.


---
This code is based on code written by the Hyperledger Fabric community. Source code can be found here: (https://github.com/hyperledger/fabric-samples). 
