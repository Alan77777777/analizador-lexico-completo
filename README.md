# Proyecto Taller de Compiladores
## Analizador Léxico

Este proyecto es un analizador léxico desarrollado para el Taller de Compiladores con el profesor Michel Emanuel López Franco. El analizador léxico reconoce los siguientes símbolos en una cadena de texto:

### Símbolos Reconocidos

- **Identificadores**: Secuencias de caracteres que comienzan con una letra y pueden continuar con letras o dígitos.
- **Enteros**: Secuencias de dígitos (`0-9`).
- **Números reales**: Números que contienen un punto decimal, con al menos un dígito antes y después del punto.
- **Operadores de adición**: `+` o `-`.
- **Operadores de multiplicación**: `*` o `/`.
- **Operador de asignación**: `=`.
- **Operadores relacionales**: `<`, `>`, `<=`, `>=`, `!=`, `==`.
- **Operador lógico AND**: `&&`.
- **Operador lógico OR**: `||`.
- **Operador lógico NOT**: `!`.
- **Paréntesis**: `(` y `)`.
- **Llaves**: `{` y `}`.
- **Punto y coma**: `;`.
- **Palabras reservadas**: `if`, `while`, `return`, `else`, `int`, `float`.

### Tipos de Tokens

Cada símbolo reconocido se clasifica en uno de los siguientes tipos:

| Símbolo          | Tipo | Descripción                               |
|------------------|------|-------------------------------------------|
| identificador    | 0    | Identificadores                           |
| entero           | 1    | Números enteros                           |
| real             | 2    | Números reales                            |
| cadena           | 3    | Cadenas de texto (no implementado)        |
| tipo             | 4    | Tipos de datos (`int`, `float`, `void`)   |
| opSuma           | 5    | Operadores de adición (`+`, `-`)          |
| opMul            | 6    | Operadores de multiplicación (`*`, `/`)   |
| opRelac          | 7    | Operadores relacionales (`<`, `<=`, `>`, `>=`) |
| opOr             | 8    | Operador lógico OR (`||`)                 |
| opAnd            | 9    | Operador lógico AND (`&&`)                |
| opNot            | 10   | Operador lógico NOT (`!`)                 |
| opIgualdad       | 11   | Operadores de igualdad (`==`, `!=`)       |
| puntoYComa       | 12   | Punto y coma (`;`)                        |
| coma             | 13   | Coma (`,`)                                |
| parentesisIzq    | 14   | Paréntesis izquierdo (`(`)                |
| parentesisDer    | 15   | Paréntesis derecho (`)`)                  |
| llaveIzq         | 16   | Llave izquierda (`{`)                     |
| llaveDer         | 17   | Llave derecha (`}`)                       |
| asignacion       | 18   | Operador de asignación (`=`)              |
| if               | 19   | Palabra reservada `if`                    |
| while            | 20   | Palabra reservada `while`                 |
| return           | 21   | Palabra reservada `return`                |
| else             | 22   | Palabra reservada `else`                  |
| $                | 23   | Fin de entrada (no implementado)          |

### Estructura del Proyecto

El proyecto consta de un único archivo HTML que contiene tanto el código HTML como el JavaScript necesario para el analizador léxico.

#### `index.html`

Este archivo incluye:

- Un campo de texto donde puedes ingresar el texto a analizar.
- Un botón para iniciar el análisis.
- Un área de resultados donde se muestran los tokens reconocidos.

### Funcionamiento

1. **Input**: El usuario ingresa una cadena de texto en el campo de entrada.
2. **Análisis**: El programa divide el texto en tokens utilizando espacios como delimitadores.
3. **Resultado**: Los tokens se clasifican según su tipo y se muestran en la página.

### Uso

1. Descarga el archivo `index.html`.
2. Abre el archivo en cualquier navegador web.
3. Ingresa una cadena de texto en el campo de entrada.
4. Haz clic en "Analizar" para ver los resultados.

### Ejemplo de Entrada y Salida

#### Entrada:
int x = 10;
float y = 20.5;
if (x < y) {
return x + y;
}

#### Salida:
Tipo 4 (int): int
Identificador (0): x
Asignación (18): =
Entero (1): 10
Punto y coma (12): ;
Tipo 4 (float): float
Identificador (0): y
Asignación (18): =
Número Real (2): 20.5
Punto y coma (12): ;
Palabra Reservada (19): if
Paréntesis izquierdo (14): (
Identificador (0): x
Operador Relacional (7): <
Identificador (0): y
Paréntesis derecho (15): )
Llave izquierda (16): {
Palabra Reservada (21): return
Identificador (0): x
Operador de Suma (5): +
Identificador (0): y
Punto y coma (12): ;
Llave derecha (17): }
