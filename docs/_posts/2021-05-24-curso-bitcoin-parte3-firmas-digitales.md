---
title: "Bitcoin y Criptomonedas. Parte 3. ¿Qué es una Firma Digital?. "
categories:
  - Bitcoin
tags:
  - curso
  - bitcoin
  - firmas digitales
  - criptomonedas

last_modified_at: 2021-05-24T14:25:52-05:00
---

# ¿Qué es una Firma Digital?
Una firma digital es como una firma en papel sólo que en forma digital. Lo que requerimos de las firmas son dos cosas. En primer lugar, al igual que una firma de papel esta pertenece a una persona y cualquiera podría comprobar su validez. Por otro lado una firma esta ligada a un mensaje, software o documento digital. El significado de esta firma es el acuerdo o aprobación de ese mensaje, software o documento. 

Para que una firma sea digital hay tres cosas a tener en cuenta:

1) **Generación de dos claves que están matemáticamente vinculadas**: Necesitamos ser capaces de generar dos claves: una clave privada para firma y una de verificación pública que se la puedes dar a cualquiera para verificar tu firma.

2) **Generación de la firma**: este algoritmo produce una firma al recibir una clave privada y el mensaje que se está firmando.

3) **Verificación**: este algoritmo comprueba la autenticidad del mensaje al verificarlo junto con la firma y la clave pública.

Estos tres algoritmos constituyen el esquema de firma digital. Bitcoin y Ethereum, utilizan un algoritmo específico para verificar transacciones, conocido como el algoritmo de firma digital de curva elíptica (ECDSA).

