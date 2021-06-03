---
title: "Bitcoin y Criptomonedas. Parte 4. Descentralizacion. Consenso distribuido "
categories:
  - Bitcoin
tags:
  - curso
  - bitcoin
  - descentralizacion
  - consenso distribuido
  - criptomonedas

last_modified_at: 2021-05-24T14:25:52-05:00
---

# Descentralización - Consenso distribuido

Los sistemas distribuidos son propensos a fallos ya sea por caídas o fallos maliciosos. Una de las estrategias  para conseguir que el sistema distribuido sea tolerante a fallos es mediante la réplica de información. El sistema de réplica de información es fiable pues la información reside en varios nodos. Sin embargo, es un reto mantener la consistencia entre los nodos que comparten información a la vez en un entorno en el que puede haber fallos. De esto se encargan los algoritmos o protocolos de consenso.

Un protocolo de consenso es un mecanismo que permite a los nodos coordinarse en un entorno distribuido. Debe garantizar que todos puedan ponerse de acuerdo respecto a una fuente única de verdad, incluso en el caso de que algunos de ellos fallen. En otras palabras, el sistema debe ser tolerante a fallas.

Un protocolo de consenso cumple con 2 condiciones:
1) Todos los nodos correctos (porque algunos de los nodos pueden ser defectuosos, o maliciosos) deben decidir sobre algún valor que seria el valor de consenso.
2) Este valor en el que están de acuerdo no puede ser un valor arbitrario. Debería ser un valor que fue propuesto como entrada por al menos uno de estos nodos correctos.

Para entender cómo podría funcionar el consenso distribuido en Bitcoin, recordemos que Bitcoin es un sistema peer-to-peer. Es decir, cuando por ej Ana quiere pagar a Juan, va a transmitir la transacción a todos los nodos que componen la red peer-to-peer. Esa transacción va a tener la firma de Ana que necesitan los otros nodos para saber que realmente vino de ella y la clave pública (hash) de Juan (dirección en la que se reciben los bitcoins).

Dado que una variedad de usuarios están transmitiendo estas transacciones a la red. El consenso al que se quiere llegar es sobre exactamente qué transacciones fueron transmitidas, y el orden en que ocurrieron estas transacciones. Estas transacciones se colocan en bloques y estos bloques se vinculan juntos en una cadena de bloques. Se podria hacer consenso sobre cada transaccion pero sería ineficiente. En su lugar se hace consenso bloque por bloque. Así que en cualquier momento dado, todos estos nodos en la red peer-to-peer tendrían la secuencia de bloques que ya han acordado. Cada nodo tendría también un conjunto de transacciones pendientes. Para estas transacciones pendientes el consenso aún no ha sucedido, por lo cual cada nodo podría tener una versión ligeramente diferente de las transacciones pendientes. 

Sabemos que la red es imperfecta. Al ser un sistema peer-to-peer no todos los pares de nodos están conectados entre sí. Tambien podría haber fallas en la red debido a mala conectividad  y esto resultaria en mucha latencia en el sistema. Una consecuencia particular de esta alta latencia, es que no hay noción de tiempo global. Significa que no todos los nodos pueden estar de acuerdo con un orden común de eventos basandose en la observación de marcas de tiempo. Esto pone limitaciones en los protocolos de consenso pero Bitcoin lo resuelve porque introduce la idea de incentivos a los participantes para que actúen honestamente (esto lo puede hacer porque es una moneda).
La otra cosa que Bitcoin hace de manera diferente es que el consenso ocurre durante un largo período de tiempo, aproximadamente una hora en el sistema práctico. Pero incluso al final de ese tiempo, no estás 100% seguro de que una transacción o un bloque haya entrado en la cadena de bloques de consenso. En cambio, a medida que pasa el tiempo, tu probabilidad aumenta cada vez más y la probabilidad de falla al hacer una suposición sobre una transacción disminuye exponencialmente.





