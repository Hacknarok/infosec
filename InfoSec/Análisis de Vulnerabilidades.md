---
aliases: [Fase de Análisis de Vulnerabilidades]
tags:    [concepto]
---

# Introducción
> [!INFO] Definición
> Analizar... las... vulnerabilidades...
^098b8f

![[Estructura de un Ataque Informático#^999a0a]]

> [!EXAMPLE] Ejemplo de ataque a una empresa que usa [[Wordpress]]
> Se descubre que una empresa usa [[Wordpress]] desactualizado en su web.
> 1. [[Reconocimiento|RECON]]
> 	- Se plantea usar una impresora para acceder a la empresa.
> 	-> Se conoce el modelo por los documentos de su basura.
> 	-> Las impresoras suelen ser un buen punto de ataque porque nadie las actualiza.
> 2. [[Análisis de Vulnerabilidades]]
> 	- Se investiga sobre ese modelo de impresora.
> 	- Se investiga sobre la versión de [[Wordpress]] de la web.
> 3. [[Explotación]]
> 	- Se ataca a la impresora a través de una vulnerabilidad de la web.
> 	- Se hace un [[Pivoting|Movimiento lateral]] de la impresora a una máquina interna.
> 	- Se crea un túnel [[HTTPS]] encriptado que conecta con la máquina del atacante.
> 4. [[Exfiltración]]
> 	- Se saca la información deseada.

# La idea que hay detrás
> [!INFO] Sí "se va a lo loco" en un [[Pentesting|Test de intrusión]]
> Hay que **probar** las medidas de seguridad ([[IDS|IDSs]], [[Honeypot|Honeypots]]...).

Cuando se obtienen todas las vulnerabilidades de un sistema en un [[Pentesting|Test de intrusión]], se realizan pruebas con todas las vulnerabilidades posibles para saber cómo solucionarlas o cómo se pueden explotar.

> [!INFO] No "se va a lo loco" en un ataque
> Hay que **evitar ser detectados** por las medidas de seguridad ([[IDS|IDSs]], [[Honeypot|Honeypots]]...).
- Un fallo en esta fase puede implicar ser descubierto y aumentar la dificultad del encargo, hacerlo imposible o terminal en la cárcel.
- Después del [[RECON]] el atacante debe tener un buen plan sobre la entrada y cómo actuar para, a partir de lo que se conoce, llegar a lo que el atacante realmente quiere.
- Un buen [[RECON]] acorta el [[Análisis de Vulnerabilidades]] y evita ser detectado.
![[APT#^be0f4c]]

> [!IMPORTANT] Lo ideal en el [[Análisis de Vulnerabilidades]] es ir a tiro fijo
> El atacante **no debe ser detectado**, para ello:
> 1. Debe saber el **tipo y versión del software** que corre en las máquinas más vulnerables.
> 2. Debe saber de esas versiones en concreto, qué **vulnerabilidades son explotables**.
> 3. Debe comprobar -intentando no ser detectado- cuál de esas potenciales vulnerabilidades **realmente van a funcionar**.

==[[WannaCry]] → [[Pedal de hombre muerto]] → Se paran todas las instancias del virus del mundo==.

![[David Santo Orcero#^136aaf]]
