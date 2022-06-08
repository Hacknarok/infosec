---
aliases: [APTs, Amenaza Persistente Avanzada, Amenazas Persistentes Avanzadas]
---

#ataque 

***

# Introducción
> [!INFO] Definición
> Consiste en un ataque que emplea técnicas persistentes para tomar el control de los sistemas, con el fin de hacer otras **acciones a medio o largo plazo y de forma contínua**.

> [!INFO] Siglas
> **A**dvanced **P**ersistent **T**hread
> *Amenaza Persistente Avanzada*

## Características
- No es un ataque puntual.
- No es utilizar una secuencia de vulnerabilidades para llegar al objetivo.
- No es un ataque tipo *entrar y salir*.

- Ataque sostenido en el tiempo.
- Requiere introducir [[Troyano|Troyanos]] y [[Aplicación Espía|Aplicaciones Espía]], además del uso de vulnerabilidades.
	- Normalmente estos [[Troyano|Troyanos]] son autónomos y producen [[Puertos en modo promíscuo]].

La **finalidad principal** es desplazar la [[Exfiltración]] del ataque.

**Siempre se descubre especialmente tarde**, pero descubrirlo pronto permite saber hasta el remitente.

Los [[APT|APTs]] suelen usarse como un *checkpoint* de un ataque. ^be0f4c

## Proceso
1. Infiltrarse en el sistema.
2. Dejar el [[APT]].
3. Huir del sistema.
4. Volver pasado un tiempo.
5. Atacar.

# Los [[APT|APTs]] en [[Pentesting]]
Los [[APT|APTs]] son extremadamente complejos, pero en [[Pentesting]] no se llega a ese nivel: lo importante es **demostrar que se puede inyectarse, no sus consecuencias**.
- No se desarrolla hasta el final, basta con demostrar vía [[PoC]] que puede instalarse.

**Una empresa no puede permitir espiar las comunicaciones privadas de los empleados ni de terceros**, es importante no dejar un [[APT]] operando *donde* y *cuando* no debe.
- Generalmente, implantarlos va a ser más parecido a una demostración con los directivos y administradores de sistemas de la empresa mirando.

# Ejemplo
Auditoría de MS Office 360 (histórico de 6 meses).
-> Si se ataca, queda registrado.
-> Si se ataca pasado 6 meses, te libras.


