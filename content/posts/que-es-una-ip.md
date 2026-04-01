---
title: "Qué es una IP y cómo funciona? - P.1"
date: 2026-03-26T17:02:42-06:00
draft: true
translationKey: "ip-01"
tags: ["Redes", "Básicos", "Infraestructura"]
categories: ["Redes"]
---

> **Informe Cobblepot:** *Toda comunicación en internet, desde enviar un mensaje por WhatsApp, hasta conectarte a una aplicación para millones de usuarios como Netflix, depende de saber quién habla con quién. Entender las direcciones IP no es solo "cosas de IT"; es el primer paso para entender como funcionan los servicios digitales, configurar páginas web o entender los cimientos de la ciberseguridad. Sin IPs, no hay negocio digital.*

---

# Entendiendo Internet desde la base: IPs

El internet puede parecer magia negra, pero en realidad funciona bajo reglas bastante estrictas y lógicas. Piensa en internet como el sistema de correos más grande y rápido del mundo.

En esta serie vamos a descomponer tres conceptos fundamentales que hacen posible que estés leyendo este blog ahora mismo:

1. Qué es una IP (y por qué se nos están acabando)
2. Cómo funcionan los puertos y las conexiones
3. Cómo se relaciona todo esto con las URLs

Vayamos por partes, como dijo jack en destripador. Empecemos con las bases.

---

## Parte 1: ¿Qué es exactamente una IP?

### El Identificador Único de tus dispositivos

Una dirección IP (*Internet Protocol*) es el identificador único de un dispositivo dentro de una red. 

### ¿Que es una red?

Piensa en la red como un edificio de departamentos con varias personas viviendo en cada piso. La red puede ser domestica (un edificio donde vive gente), corporativa (un edificio de oficinas), o pública (un centro comercial). 

Cada una de estas redes se rigen bajo ciertas reglas específicas, pero para efectos prácticos, nos centraremos en redes domesticas, el edificio donde viven personas, o en nuestro caso... El modem que está dando internet en tu casa.

Sin la red, tu computadora (o celular) sería como una persona que intenta recibir correspondencia en ese edificio, pero el cartero no tiene dirección física a donde entregarla; los datos (cartas en este ejemplo) simplemente no sabrían cómo llegar.

Piensa en una IP, como **un número único e irrepetible** dentro de un mismo entorno. Tu celular, tu Smart TV, tu refrigerador inteligente... todos tienen una. En el ejemplo de los departamentos, no puede existir dos departamentos con el número 1 (en un escenario perfecto), si hubieran 2 departamentos con el mismo número, probablemente compartirían más allá de solo el número, por ejemplo, las facturas; En el caso de la red, compartirían la información si hay 2 iguales.

---

### ¿Cómo se ve una IP? ¿Que forma parte de una IP?

Si no tienes conocimiento previo, podrías pensar que una IP es algo místico, o una dirección física como en el ejemplo de los departamentos. En realidad no es más que una forma matemática, de los años 80, en la que se le dió solución a un problema muy grande: ¿Cómo podemos comunicarnos con otras personas por internet?

Te presento, una IP en el formato IPv4 (no te preocupes, entenderás esto más adelante):

`192.168.1.1`

Esta IP, está formada por 4 secciones separadas por puntos. A cada sección se le llama *octeto*. Los números dentro de cada octeto pueden ir del 0 al 255. (Y sí, existe la IP `1.1.1.1` y en este momento le pertenece a "Cloudflare").

Puede que te hayas preguntado, por qué un "octeto", se llama "octeto"... Bueno, un octeto es una unidad de información digital formada por 8 bits. 

Un bit (o dígito binario) es la unidad más pequeña en la computación, siendo que cada bit solo puede valer 0 o 1, lo que resulta en que las combinaciones posibles pueden ir de `00000000` (8 veces 0) a `11111111` (8 veces 1). 

Puede que también te hayas preguntado, por qué un octeto solo puede ir del 0 al 255, bueno... si aplicamos un poco de matemáticas podemos obtener cuantas combinaciones exactas tiene un octeto:

Un bit consta de únicamente 2 posibilidades, 0 y 1. Esta será nuestra constante "2" llamada "posibilidades".

Cada octeto consta de 8 bits, o sea, 8 combinaciones posibles entre 0 y 1, una por cada bit. Esta será nuestra constante "8" llamada "número de bits".

La formula es simple, contante ^ número de bits: 

2^8 = 256 posibilidades.

Por eso cada octeto puede ir del 0 al 255, siendo 0 = `00000000` y siendo 255 = `11111111`.

A su vez, estos octetos o grupos de 8 bits, se les conoce comunmente como *byte*, que es una unidad de medida más grande, formada por 8 bits. O sea que nuestra dirección IP que contiene exactamente *4 octetos* o *32 bits*, es a su vez *4 bytes* de información. 

---

### El gran error de las IP's

Imagina que son los años 80's, es el inicio del internet tal cual como lo conocemos, y la cantidad de personas que tienen acceso a este servicio, son pocas y muy limitadas por ser un invento reciente.

Pasan los años, conforme la tecnología avanza, van agregandose más y más y más dispositivos conectados a la red.

* Ahora, conociendo que las IP's no son ilimitadas y están topadas por la estructura de 4 octetos diferentes.
* Lo que esto nos permite al rededor de unas ~4.3 mil millones de direcciones posibles.
* En el año 1983 se creó el protocolo TCP/IP con la primer versión  oficial de la IP de 4 octetos (IPv4).
* Para 1990 habían 5.27 mil millones de personas en todo el mundo. 
* El internet se abrió al acceso público (World Wide Web) el 23 de agosto de 1991.
* En 1990 habían (aproximadamente) 2.61 millones de usuarios navegando en internet.
* Para 1995 ya habían (aproximadamente) a 39.2 millones de usuarios. Lo que corresponde a un aumento del *1401.916%* en 5 años.
* Si el incremento de usuario navegando en internet seguía con esta velocidad fija, significaría que para el año 2000 habrían 549.2 millones de usuarios. (Suponiendo que solo se tuviera 1 dispositivo por usuario conectado al internet, sin contar empresas con N cantidad de dispositivos conectados y sin contar los dispositivos que estaban conectados pero sin usuario específico como los servidores.)
* Con esto en mente, era muy obvio que tarde o temprano las direcciones IP se iban a acabar en todo el mundo, y que pasaba si se acaban? Los nuevos dispositivos que necesitaran conectarse no tendrían una dirección a la cual conectarse a la red mundial.

- ¿Cómo solucionarías este problema?

### ¿Pública o Privada? Que pasa si existen 2 edificios diferentes, pero ambos tienen un departamento "1"?

Para lidiar con el hecho de que nos quedamos sin direcciones IPv4, se inventó algo brillante pero que tarde o temprano sufriría el mismo destino. Separar las IP's en públicas y privadas.

* Volvamos al ejemplo del edificio, en este preciso instante estás viviendo en un departamento con número en la puerta "21".
* Necesitas recibir un paquete y pones tu dirección como "departamento con puerta 21".
* El repartidor llega, pero hay una sorpresa gigante, en tu lugar de residencia hay 20 edificios como el tuyo y todos tienen un departamento con el número "21", cómo es posible que alguien pueda encontrar tu dirección sin tener una posibilidad de 1/20 de tener un error.
* Imagina que pasa lo mismo en el internet y estás mandando un mensaje, pero no llega al receptor, sino que llega a otra persona, y un mensaje que no era para ti, te llega... Caotico, cierto?

 **Te presento la división sobre las "IP's". (Que es el mismo principio que se utiliza en los edificios de departamentos en la vida real).**

* **IP Pública:** 
* * Es la cara de tu red hacia el mundo exterior (Internet). 
* * Tu proveedor de internet te asigna *una sola* de manera automática al contratar el servicio directamente en tu "Modem" o "Router".
* * Siguiendo el ejemplo de los edificios, este número es el número de referencia exterior que está por fuera de tu edificio.

* **IP Privada:** 
* * Funciona solo de puertas para adentro (en el Wi-Fi de tu casa o empresa). 
* * Tu router o model se encarga de asignarlas a cada uno de los dispositivos que se conectan a ese Wi-Fi. 
* * Son los números de los departamentos dentro del edificio, así puede existir un edificio 3 con departamento 22 y el proveedor sabrá como llegar si le das ambas.

> **Dato curioso:** Tu celular y tu laptop probablemente tengan la misma IP Pública en este momento (la del router de tu casa), pero tienen IPs Privadas diferentes para que no choquen entre sí. Viven en el mismo edificio, pero son parte de diferentes departamentos, a ambos les debe llegar correspondencia pero puede que no sea la misma ni al mismo tiempo.

---

### ¿Cómo se ve una IP Privada?

Tomemos este ejemplo clásico que probablemente veas cuando se hablan de direcciones IP privadas:
`192.168.1.25`

No es solo un número al azar. Se divide en dos partes principales, separadas invisiblemente por algo llamado "máscara de subred":

1.  **Red (Network):** Identifica a qué "vecindario" o red pertenece el dispositivo. En este caso, el vecindario es `192.168.1`.
2.  **Host (Dispositivo):** Identifica el equipo específico dentro de ese vecindario. En este caso, eres el dispositivo número `25`.

De esa forma es en la que tus dispoitivos pueden conectarse a tu Wi-Fi, cada una se le asigna un "Host" bajo la misma "Red".

* ¿Pueden haber 2 IP's en la misma red que copartan Host? Absolutamente No.
* ¿Qúe numeros pueden estar en el host? va desde el 1 hasta el 254.
* ¿Por qué no está el 0 ni el 255? Bueno, estos son 2 direcciones de host reservadas para objetivos especiales dentro de tu red de Wi-Fi. (En realidad para tu router, pero es tema de otro día.)
* ¿Cómo se verían 2 dispositivos en la misma red? Ej. 192.168.1.104 y 192.168.1.200

---

### ¿Cómo consigues el número de identificación de tu "departamento"?

Existen dos formas principales en las que un dispositivo que se conecta a un Wi-Fi obtiene su IP:

* **Estática (Manual):** 
   * Se configura a mano y nunca cambia. 
   * Es vital para servidores web, impresoras de oficina o cámaras de seguridad, porque necesitas saber siempre dónde encontrarlos.

* **Dinámica (Automática):** 
   * Se asigna sola gracias a un protocolo llamado DHCP. 
   * Cuando llegas a una cafetería y te conectas a su Wi-Fi, el router te "presta" una IP por un rato. Cuando te vas, se la da a alguien más.
   * Cada vez que te conectas y desconectas de un Wi-Fi, es muy probable que tu IP privada cambie.

---

### Que pasa si se acaban las IP's públicas?

Ya hicimos las metemáticas, ya platicamos de la historia y probablemente te surgió una duda:
- "Si las IP's tienen un límite en cantidad, se pueden acabar las IP's públicas?"

La respuesta a tu pregunta, es un rotundo 'SI'. Pero también tenemos una solución al problema de haber subestimado el tamaño de internet.
Te presento las 2 versiones que existen de IP's.

### IPv4 (La vieja confiable)
Es la que ves todos los días. 
* **Formato:** `192.168.1.1`
* **Anatomía:** 4 bloques numéricos, separados por puntos, que van del 0 al 255.
* **Capacidad:** Nos permite unas ~4.3 mil millones de direcciones posibles.
* **El Gran Problema:** En los años 80 parecía una infinidad. Hoy, con cada persona teniendo un celular, laptop y reloj inteligente, **ya nos quedamos sin ellas**.

### IPv6 (La salvadora)
Nació para solucionar el problema de escasez.
* **Formato:** `2001:0db8:85a3:0000:0000:8a2e:0370:7334`
* **Anatomía:** 8 bloques alfanuméricos (hexadecimales) separados por dos puntos.
* **Capacidad:** Absurdamente gigante. Hablamos de ~340 undecillones de direcciones. Podríamos asignarle una IP a cada átomo de la superficie de la Tierra y aún sobrarían. Está diseñada para sostener el Internet de las Cosas (IoT) por siglos.


En el día a día es muy probable que escuches mucho a cerca de las versiones antiguas (IPv4), especialmente en servidores. 

Si existe una versión con esteroides, muchisimo mejor y que tiene más capacidad... ¿Por qué seguimos ocupando la versión anterior?

Bueno, resulta que la implementación de esta versión, es compleja ya que tiene una falta de compatibilidad con su hermana mayor (IPv4), a demás de barreras técnicas y sobre todo económicas para migrar de uno a otro, se inventaron tecnologías "dual-stack" para poder tener a ambas versiones coexistiendo, inclusive, en la misma red. (Tu celular tiene una dirección IPv6 asignada por defecto).

---

### En resumen...

Imagina el sistema postal:
* **La IP Pública** es la dirección de tu edificio residencial.
* **La Red (Network)** es el bloque de departamentos.
* **El Host** es tu número de departamento específico.
* **Dinámico/Estático** es la diferencia entre rentar un Airbnb por un día o comprar tu casa propia.

En el próximo post, veremos qué pasa una vez que la carta llega a tu casa y cómo los **Puertos** se aseguran de que se la entreguen a la persona correcta.