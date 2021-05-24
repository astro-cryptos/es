---
title: "Bitcoin y Criptomonedas. Parte 1. Funciones Hash. "
categories:
  - Bitcoin
tags:
  - curso
  - bitcoin
  - hash
  - criptomonedas

last_modified_at: 2021-05-17T14:25:52-05:00
---

# Funciones HASH
Una función Hash es una función matemática que tiene 3 propiedades:

1. Puede tomar cualquier cadena de cualquier tamaño como entrada.
2. Produce una salida de tamaño fijo.
3. Tiene que ser eficientemente computable, es decir, dada una cadena se puede averiguar cuál es la salida en un tiempo razonable. 

Las funciones Hash se pueden dividir en 
- **No criptográficas**, que son las utilizadas por software para encontrar archivos rápidamente al utilizar información más comprimida.
- **Criptográficas**, que modifican los datos de un documento con el objetivo de alcanzar algunas características de seguridad y son las utilizadas por Bitcoin.

Hay distintas funciones Hash y cada una tiene diferentes normas para codificar las entradas, por ejemplo MD5, SHA-1, SHA-2, etc. La que utiliza Bitcoin es la llamada SHA-256 (Secure Hashing Algorithm 256 bits), que es criptográfica y es utilizada para transformar las diferentes transacciones (Mensajes de un tamaño cualquiera) de Bitcoin en bloques, es decir en archivos de un tamaño fijo. Para ser seguras estas funciones Hash deben cumplir con 3 propiedades:

1. **Libre de colisiones**:
Significa es que es imposible encontrar valores "x" y "z" que sean diferentes y que la función Hash de ellos sean iguales.
Es decir, es muy difícil, encontrar que dos entradas "x" y "z"  resulten en la misma salida. Si esto se diera se produciría una colisión. No significa que no hay colisiones, sino que nadie las puede encontrar. Sabemos que las colisiones existen pero la pregunta es ¿hay alguna colisión que sea encontrable por personas normales que usan computadoras normales?.

2. **Ocultamiento**:
Esta propiedad hace posible que la función Hash sea no invertible. Es decir, dado H(x) es imposible saber cual es "x" (la entrada). El problema es que esta propiedad no se mantiene exactamente. Veamos este ejemplo. Si tiramos una moneda al aire y el resultado es "cara" vamos a devolver el Hash de la cadena "cara" y si fue "cruz" podemos devolver el Hash de la cadena "cruz". Luego le pedimos a alguien que no vio la tirada de la moneda, pero solo vio esta salida Hash, que averigue cuál era la cadena de entrada al Hash. Eso es fácil. Simplemente calcula el Hash de la cadena "cara" y el Hash de la cadena "cruz" para averiguar qué era "x". Así que la razón por la que este ejemplo falló es que  solo había un par de valores posibles de "x". Por lo tanto, para que no falle, "x" tiene que ser elegido de un conjunto que este muy extendido. 
Esto se soluciona anteponiendo a la entrada "x" (en el ejemplo "cara" o "cruz"), un número aleatorio "r" conocido como llave (key), elegido de una distribución estadística con un alto grado de incertidumbre. Es decir se concatena a la "x" este numero, quedando una funcion quedando de esta manera:

   H(039429374171591003cara) = 0x5e77r3fe3feefr3r1c

   Esta funcion toma todos los bits de "r", y pone después de ellos todos los bits de x. Y entonces lo que vamos a decir es dado el Hash de r junto con "x" es inviable encontrar "x". Entonces, siempre y cuando "r" se eliga de esa manera, entonces el Hash de "r" concatenado con "x" ocultará "x".

   La propiedad 1) asegura que solo hay una solución y la 2) hace imposible encontrarla.

3. **Puzzle friendly**:
    Para cada salida Hash "y" dentro del rango de valores de "Y" y una entrada "x" no es factible encontrar un valor "k", que resultará en h(kx)=y. Esta propiedad se diferencia de la 2) en que la "k" en este caso es dada, nos dan el PUZZLE-ID. Y segundo, se menciona un rango de valores "Y". Por lo que se podría reformular diciendo, que para resolver el puzzle, se debe encontrar una "x" que genere un resultado que caiga en el intervalo de "Y". Si hay más posibles resultados de "y", hay más posibles soluciones "x", por lo que hay más probabilidades de encontrar una. Es decir, que la dificultad del puzzle depende directamente del tamaño que tiene el rango "Y" en ese momento y no nos extenderíamos buscando la solución "x" hasta un tiempo infinito si la dificultad no es máxima. Esta propiedad hace posible la minería. Es la base de la blockchain.

