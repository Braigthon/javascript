# Fundamentos de Javascripts

## tipos de datos

### Number
Representan numeros enteros tanto con decimal 
Ademas de aceptar *(multiplicion) /(division) +(suma) -(resta) 

  #### Valores numericos especiales:

    * Infinity 
      Un numero matematico infinito sea determinado por un ecuacion o un simplemente "infinity" 
    * -infinity 
      (no se explico aun) 
    * NaN(Not A Number) 
      Basicamente cuando un ecuacion falla o es incorrecta es NaN 
___

### Bigint
En javascript no existen valore mayores a  

(253-1) que es 9007199254740991 o -9007199254740991 
mas alla de eso solo dara valores incorrectos con pares 

Para usar numeros mas grandes necesitamos agregar una "n" al final de esta cifra para que se lea como un big int 
 
- **Solo es aceptado por ciertos navegadores como chrome/firefox etc..**
___

### String
Es una cadena de caracteres que deben ser puestos en comillas, existen tres tipos de comillas reconocidas en javascrist:
1. Comillas dobles: "Hola" 
2. Comillas simples: 'Hola' 
3. Backticks (comillas invertidas): `Hola`. 

Las comillas dobles y simples se leen igual 
Sin embargo los backticks tiene funcionalidad extendida 

  #### Backticks
  Los backticks son comillas de “funcionalidad extendida”. Nos permiten agregar variables y expresiones en una cadena de caracteres encerrándolas en ${...} 
~~~
<!DOCTYPE html> 

<script> 

let name = "John"; // incrustar una variable 

alert( `Hola, ${name}!` ); // Hola, John! // incrustar una expresión 

alert( `el resultado es ${1 + 2}` ); //el resultado es 3 

</script> 
~~~
___
Falta informacion arriba

## Ejecucion condicional

en ciertos casos es necesario usar la condicional "if" para ejecurtar 1 o mas acciones o en todo caso el operador condicionale "?"

### sentencia "if"
la sentencia "if" evalua un condicion cerrado en un parentesis si el resultado es vedadero ejecuta cierto bloque de codigo
por ejemplo:
  ```
            let year = prompt('In which year was ECMAScript-2015 specification published?', '');
            if (year == 2015) alert( 'You are right!' );
  ```
ahora un ejemplo mio modificado:
  ```
            let year = prompt('In which year was ECMAScript-2015 specification published?', '');

            if (year == 2015) {
            alert( 'You are right!' );}

            if (year !== 2015) {
            alert( 'whats going on?' );}
  ```
se recomenda encerrar el codigo entre llaves "{}" para poder hacer una mejor lectura del codigo

### conversion a booleano
if (...) evalua la expresion en los parentesis y lo convierte como resultado en un booleano
  
- recuerda que todos los los valores como (0, "", null, undefined, Nan) seran Falsos y cualquier
  otro numero sera True

en estos casos el codigo en esta condicion nunca se ejecutaria:
    if (0) { // 0 es falso
  ...
  }
y en esta posicion siempre se ejecutara
    if (1) { // 1 is truthy
  ...
  }

### la clausale else
en caso de que tu condicionante if sea falsa.. en es momente else se ejecutara 
por ejemplo:
          ```
          let year = prompt('In which year was the ECMAScript-2015 specification published?', '');

          if (year == 2015) {
            alert( 'You guessed it right!' );
          } else {
            alert( 'How can you be so wrong?' ); // any value except 2015
          }
          ```
### varias condiciones: "else if"
en algunas ocasiones necesitaremos tener muchas variantes de un condicion, en estos casos "else if" te dejara hacer eso...
          ```
          let year = prompt('In which year was the ECMAScript-2015 specification published?', '');

          if (year < 2015) {
            alert( 'Too early...' );
          } else if (year > 2015) {
            alert( 'Too late' );
          } else {
            alert( 'Exactly!' );
          }
          ```
en este caso, el final "else" es opcional y tambien funcionaria como el final de la condicional "else if"

### operador condicional: "?"
 el operador condicional nos ofrece agregar una variable o mejor dicho 2 valores a un cuestionamiento.
 por ejemplo:
              ```
              let accessAllowed;
              let age = prompt('How old are you?', '');

              if (age > 18) {
              accessAllowed = true;
              } else {
              accessAllowed = false;
              }
              ```
esto podria ser mas practico con el uso de la condicional "?"
              ```
              let accessAllowed = (age > 18) ? true : false;
              ```
### multiple condiconal "?"
el condicional multiple te permite agregar tantos condicionales como deses para agregar mas valores condicionadas
por ejemplo:
            ```
            let age = prompt('¿edad?', 18);

            let message = (age < 3) ? '¡Hola, bebé!' :
            (age < 18) ? '¡Hola!' :
            (age < 100) ? '¡Felicidades!' :
            '¡Qué edad tan inusual!';

            alert( message );
            ```
que por otro lado con else if seria asi:
            ```
            if (age < 3) {
              message = '¡Hola, bebé!';
            } else if (age < 18) {
              message = '¡Hola!';
            } else if (age < 100) {
              message = '¡Felicidades!';
            } else {
              message = '¡Qué edad tan inusual!';
            }
            ```
### uso con tradicional de "?"
aunque el uso de la condicional es mas facil de usar se recomienda hacer uso del if para una mejor compresion del codigo

## operadores logicos
hay cuatro operadores logicos en javascript: || (O), && (Y), ! (NO), ?? (Fusión de nulos). Aquí cubrimos los primeros tres, el operador ?? se verá en el siguiente artículo.

  ### || (OR)
  En la programación clásica, el OR lógico esta pensado para manipular solo valores booleanos. Si cualquiera de sus argumentos es true, retorna true, de lo contrario retorna false.

  En JavaScript, el operador es un poco más complicado y poderoso. Pero primero, veamos qué pasa con los valores booleanos.

  Hay cuatro combinaciones lógicas posibles: 
            ```
            alert(true || true); // true (verdadero)
            alert(false || true); // true
            alert(true || false); // true
            alert(false || false); // false (falso)
            ```
  La mayoría de las veces, OR || es usado en una declaración if para probar si alguna de las condiciones dadas es true
            ```
            let hour = 9;

            if (hour < 10 || hour > 18) {
              alert( 'La oficina esta cerrada.' );
            }
            ```
  Otro ejemplo con mas condiciones seria:
            ```
            let hour = 12;
            let isWeekend = true;

            if (hour < 10 || hour > 18 || isWeekend) {
              alert("La oficina esta cerrada."); // Es fin de semana
            }
            ```
  ### OR "||" encuentra el primer valor verdadero
  La lógica descrita arriba es algo clásica. Ahora, mostremos las características “extra” de JavaScript.

El algoritmo extendido trabaja de la siguiente forma.
Dado múltiples valores aplicados al operador OR:
            ```
            result = value1 || value2 || value3
            ```
-Evalúa los operandos de izquierda a derecha.
-Para cada operando, convierte el valor a booleano. Si el resultado es true, se detiene y retorna el valor original de ese operando.
-Si todos los operandos han sido evaluados (todos eran false), retorna el ultimo operando.

  En otras palabras, una cadena de OR "||" devuelve el primer valor verdadero o el último si ningún verdadero es encontrado.
  