---
title: "Organizando Buk CTF"
date: 2026-09-01T21:57:06-0400
draft: false
toc: false
---

# ¿Qué es un CTF y por qué lo hicimos?

El pasado jueves, junto a Nico, organizamos un CTF dentro de Buk Finanzas. La instancia contó con la participación de gran parte del equipo de desarrollo y dejó en evidencia la curiosidad, la competitividad y un poco de obsesión de nuestros colegas con los desafíos.

Para quien no esté muy familiarizado con el término, un CTF (_Capture The Flag_) es una competencia de ciberseguridad en la que se presentan varios desafíos, cada uno con un puntaje asignado. Los desafíos consisten en un entorno simulado con fallas intencionales, lo que permite aprender a detectar vulnerabilidades mientras se juega. A medida que los participantes los resuelven, van acumulando puntos, y el ganador es quien obtiene más puntaje dentro de un intervalo de tiempo determinado. En este contexto, resolver un desafío implica encontrar una _flag_, un trozo de texto con el formato `FLAG{s0me_1nteresting_c0nt3nt}`.

La idea nació mientras pensábamos en qué presentar en nuestros _Webinars Devs_. Tanto Nico como yo habíamos participado en CTFs durante nuestra época universitaria, como parte del CLCERT (Laboratorio de Criptografía Aplicada y Ciberseguridad de la UChile). Allí era relativamente común participar en este tipo de instancias, tanto para aprender, como para también desafiarnos y representar al laboratorio. 

Se nos ocurrió que organizar un CTF dentro del equipo podía ser una buena manera de despertar un poco el pensamiento _hacky_ y volvernos más conscientes de las posibles vulnerabilidades que pueden abrirse a medida que desarrollamos. Además, pensábamos que la instancia sería algo distinto a lo habitual y le daría un carácter más interactivo a la charla.

Entonces, ya estaba la idea: una breve charla sobre hacking ético y los CTF, seguida de un _hands on_. La cuestión ahora era llevarla a algo concreto.

## La idea en acción

En un principio, pensamos hacer algo simple: una charla de 20 minutos y luego añadir 3 desafíos básicos a la presentación para que las y los asistentes los resolvieran. La primera persona en hacerlo debía exponer su solución y así tod@s aprendíamos. 

El problema era que ese formato le quitaba mucho de la emoción, acortaba la ventana de tiempo, reducía la sensación de competencia real y, sobre todo, restaba la gamificación que considerábamos tan valiosa. Fue ahí cuando pensamos: "¿y si la hacemos en grande?". Pedimos un poco más de plazo para nuestra charla (¡gracias, Isma!) y nos pusimos a trabajar en serio.

## Herramientas y logística

Descubrimos que existe un repositorio de código abierto llamado [CTFd](https://github.com/CTFd/CTFd), que se encarga de la aplicación que aloja toda la competencia: el registro de usuarios, la creación de desafíos, la asignación de puntajes, y todo lo demás. De verdad nos salvó la vida esta plataforma, porque casi la armamos desde cero; sin ella, habría sido una versión muy rústica y con una experiencia de usuario mucho más deplorable. 

Lo siguiente fue buscar dónde hostear todo. Necesitábamos un servidor. Consideramos por un momento usar la cuenta de AWS de la empresa y levantar un EC2 efímero, pero honestamente nos dio un poco de miedo las implicancias que eso podía tener. Al final, optamos por pagar por un VPS propio, cotizamos en varios lados y nos quedamos con Hostinger. Muy buena experiencia de usuario; incluso nos regalaron un dominio. ¿Qué mejor?

## Diseñando los desafíos

Teniendo el servidor listo, faltaba lo principal: los desafíos. No podía ser cualquier cosa, porque era un CTF introductorio y no podíamos asumir conocimientos de herramientas ni teoría propios de un CTF estándar. Además, queríamos orientarlo a nuestra área de trabajo (desarrollo web), sin dejar de lado temáticas como OSINT, STEGO y forense (si les interesa, pueden buscar en qué consisten 👀).

Así surgió un brainstorming de ideas:

- "Podría ser una app web en cuya _request_ principal pase esto"
- "Podríamos armar una mini red social con alguien que exponga demasiada información personal"
- "Podría ser un algoritmo de encriptación mal utilizado"
- "En el CTF de X vez había un desafío que se trataba de esto, repitamoslo acá"
- y así un largo etcétera.

Tras ello, tocó llevarlo a lo concreto: subir a la plataforma los desafíos estáticos con los recursos necesarios, o bien programar aplicaciones web con vulnerabilidades intencionales. Aquí hubo mucho _vibe coding_, a decir verdad. Después de mucho esfuerzo, logramos armar una batería de 13 desafíos:

![challenges](/posts/challenges-bukctf.png)

Para la presentación, nos basamos en los apuntes del curso ["Taller de Hacking Competitivo"](https://tallerdehacking.dcc.uchile.cl/docs/prologo/intro/) del DCC UChile, tomando extractos bastante descarados para algunas _slides_, a decir verdad.

## El día de la charla

Teníamos todo listo y estábamos entre nerviosos y emocionados. ¿Y si no les gusta? ¿Y si lo encuentran fome? ¿Y si se frustran demasiado? ¿Y si lo encuentran muy fácil? Un montón de dudas y una sola forma de resolverlas: llegar a la charla y ver nosotros mismos el efecto de nuestro trabajo.

La parte más "catedrática" de la charla fue bastante fluida. Pudimos introducir los conceptos básicos, la dinámica y el flujo general de un CTF. Nos demoramos unos 20 minutos en explicar todo, bastante certero en retrospectiva. 

Luego venía lo más chido. Dispusimos un enlace para que todas y todos pudieran registrarse en la competencia, con 1 hora completa (en teoría) para resolver la mayor parte de los desafíos posibles. Desde ese punto, la charla terminaba y cada uno empezó su camino. Igualmente, estuvimos paseándonos por cada puesto de trabajo y atentos al chat por si surgían dudas.

## Cómo reaccionó la gente

A medida que se desarrollaba el CTF, nos encontramos con distintas reacciones: algunas de frustración por no entender muy bien el asunto, otras de curiosidad por esta nueva dinámica, y también gente que se tomó muy en serio la competencia. 

Para ir resolviendo algunas cosas, fuimos soltando pistas por desafío a cambio de una cantidad minúscula de puntos, como premio a quien lo resolvía sin pistas. En retrospectiva, no fue la mejor idea, porque muchos sentían "honor" en resolverlo sin usar pistas y preferían no resolverlo antes que usar una pista de "deshonor".

![dishonor](/posts/dishonor-mulan.png)

Quizás pudimos pensar mejor en cómo manejar las pistas. Fuera de eso, notamos que más gente empezó a motivarse. Algunos se quedaron participando del CTF incluso cuando terminó la hora establecida, y otros incluso se pusieron a resolver desafíos a altas horas de la noche (les tkm).

## Reflexión final

En retrospectiva, creemos que la instancia fue de agrado del equipo de desarrollo. Hay cosas que pudimos haber hecho mejor, como introducir ejemplos prácticos antes de la competencia real o indicar en qué fijarse en general. Algunos tips, quizá. Pero, fuera de todo, creemos que fue una instancia de mucha entretención y aprendizaje y que cumplió completamente su objetivo.

Fue lindo despertar la curiosidad de más gente. Quizás algunos no quieran volver a participar en un CTF nunca más en su vida, porque no les gustó, y me parece válido. Pero también rescato que otros quizá hasta se motiven a participar en algún CTF externo eventualmente o a seguir aprendiendo por su cuenta.

Espero que podamos armar una instancia parecida en el futuro. Y a quien esté leyendo esto fuera de Buk Finanzas, les invito a que se animen a organizar o participar en un CTF. Estoy seguro de que van a aprender más de alguna cosa y que lo pasarán bastante bien :)

### Algunos CTF en Chile
- [SheSecures](https://shesecures-chile.hackrocks.com/) organizado por la ANCI y OEA.
- [Campo de Marte](https://www.campodemarte.cl/) organizado por Duoc UC, Inacap, AIEP y UTFSM.
- Hack.ING organizado por Security UC Club.
