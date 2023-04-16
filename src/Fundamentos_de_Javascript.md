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
