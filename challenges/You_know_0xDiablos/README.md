# You know 0xDiablos - Pwn (20 Points)

## Descripción
Este reto consiste en la explotación de un binario vulnerable con una función `gets()` que permite un desbordamiento de buffer (BoF). El objetivo es modificar el flujo de ejecución para llamar a una función que imprime el contenido del archivo `flag.txt`.

## Procedimiento
1. **Análisis del binario**:
   - Se utilizó `gdb` para desensamblar la función `main` y `vuln`.
   - Se identificó una llamada a `gets()`, lo que indica la posibilidad de un BoF.
   - Se encontró una función `flag()` que nunca es llamada.
2. **Identificación del exploit**:
   - Se determinó que el buffer requiere 188 bytes antes del return address.
   - Se estableció la dirección de `flag()` y se insertaron los valores `0xdeadbeef` y `0xc0ded00d` en los lugares adecuados en la pila.
3. **Construcción del exploit**:
   - Se escribió un script en Python utilizando `pwntools` para enviar el payload y obtener la bandera.
   - Se probó en un entorno local y luego en la instancia de HTB con `netcat`.

## Código de explotación
Ver archivo `exploit.py` en este directorio.

## Herramientas utilizadas
- `gdb`
- `pwntools (Python)`
- `netcat`
- `cat`

## Debilidades explotadas
- **CWE-561**: Dead Code
- **CWE-20**: Improper Input Validation

## Patrón de ataque
- **CAPEC-153**: Input Data Manipulation

## Bandera obtenida
```
HTB{0ur_Buff3r_1s_not_healthy}
```
