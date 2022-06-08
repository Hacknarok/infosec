---
tags: [herramienta]
---

> [!TIP] Muy útil para aprender.

> [!EXAMPLE] Ataque realista en [[Metasploitable 2]] sobre una base de Datos [[MySQL]] abierta
> 1. Acceder a la base de datos, porque está abierta.
> 2. Ejecutar `SELECT * FROM users;`.
> 3. Se obtienen los [[Hash|códigos hash]] de las claves.
> 4. Usando `hash_identifier` se descubre que son de tipo [[MD5]].
> 5. Como [[MD5]] puede romperse, se obtienen la contraseñas.
> 6. Se realiza un [[Escalado de privilegios|escalado de privilegios]] con los *usuarios* y las *contraseñas*.
