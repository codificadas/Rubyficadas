Los ingredientes para programar
===

Esta sesión esta dedicada para platicar sobre los elementos esenciales para programar.

Haz un programa en Ruby
---
Antes de comenzar tienes que saber como hacer un programa.

1. Abre tu editor de texto
2. Crea un nuevo archivo
3. Escribe: puts 1+2
4. Guarda el archivo como: elnombrequequieras.**rb**
5. Ejecuta tu programa desde consola ejecutando: **ruby** elnombrequequieras.**rb**

**No pierdas de vista**


Todos archivos que contengan código Ruby deben llevar como extensión **.rb** es super importante que siempre tengas en cuenta esto porque sino no podremos ejecutar nuestro programa.

Igualmente recuerda que la computadora es super tonta y que sino la colocas en el directorio donde se encuentra tu archivo(dentro de la terminal/consola) nunca lo va encontrar, entonces recuerda siempre el comando **cd** (change directory - cambia de directorio) y pones la ruta de tu archivo.

Numeros
---
Te preguntaras que hace **puts**, 1+2 sabemos que es 3. Entonces **puts** simplemente imprime el resultado de la operación que le estamos indicando, es este caso es una simple suma. Mas adelante veras que puede servir para muchas otras cosas.

**Aritmetica simple**
Para realizar operaciones aritméticas simples en un programa usamos estos caracteres: +, -, *, /.

Vamos a jugar un poco, escribe en tu programa:

     puts 3 + 4
     puts 9 - 4
     puts 5 * 10
     puts 9 / 2
    
Guarda y corre tu programa ejecutando: ruby elnombrequequieras.**rb**
    
Debes ver como resultado:

     7
     5
     50
     4

**Tipos de números**

A pesar de que Ruby te ahorra el trabajo de definir los tipos de datos el identifica cada uno, por ejemplo escribe en tu programa:

     puts 3.0 + 4.0
     puts 9.0 - 4.0
     puts 5.0 * 10.0
     puts 9.0 / 2.0
    
Guarda y corre tu programa ejecutando: ruby elnombrequequieras.**rb**
    
Debes ver como resultado

     7.0
     5.0
     50.0
     4.5
    
Nota que el resultado de la division cuando lo escribimos sin decimales fue **4** pero cuando lo hicimos con decimales fue **4.5** aquí Ruby esta identificando entre enteros y flotantes (decimales).

Conclusión si tu operación la estas realización con enteros el resultado sera entero y si la estas haciendo con flotantes el resultado sera flotante.

**Pregunta existencial:** que pasa si sumo un entero con un flotante?
    

Letras
---
Así como **puts** nos sirvió para imprimir los resultados de nuestras operaciones, nos servirá para imprimir nuestras letras. Ahora para imprimir una palabra simplemente tenemos que escribir:

     puts "Hola Rubyficadas"
    
Guarda y corre tu programa ejecutando: ruby elnombrequequieras.**rb**

Debes ver como resultado:

     Hola Rubyficadas
    
Todo lo que queramos definir como texto en nuestro programa lo tenemos que escribir entre comillas, pueden ser simples (') o dobles (").

En Ruby un grupo de letras le llamamos **String**.

**Aritmética con palabras**
Así como podemos hacer aritmética con números lo podemos hacer con palabras (Strings) es decir podemos agregar palabras a nuestras palabras, vamos a intentar.

Escribe en tu programa:

     puts "Me gusta " + "las zarzamoras"
     puts "Me gusta"+" las zarzamoras"
    
Guarda y corre tu programa ejecutando: ruby elnombrequequieras.**rb**

Debes ver como resultado:

     Me gusta las zarzamoras
     Me gusta las zarzamoras
    
La función del **+** es concatenar (unir) las dos palabras.

**OJO** fíjate como solo esta considerando los espacios dentro de las comillas y no los que están fuera de estas.

Sin embargo hay otra forma mas practica de concatenar palabras, la grandiosa **interpolación**. Para usarla necesitamos esta se representa de esta forma: "En un año hay #{4*12} semanas". Todo lo que se encuentre dentro de los corchetes ({}) tiene que ser código que Ruby pueda entender.

Escribe en tu programa:
    
     puts "Un día tiene #{24*60} minutos"

Guarda y corre tu programa ejecutando: ruby elnombrequequieras.**rb**

Debes ver como resultado:
    
     Un dia tiene 1440 minutos    


Ahora vamos hacer volar tu mente multiplicando Strings.

Escribe en tu programa:

     puts "Somos lo máximo! " * 3
    
Guarda y corre tu programa ejecutando: ruby elnombrequequieras.**rb**

Debes ver como resultado:
    
     Somos lo máximo! Somos lo máximo! Somos lo máximo!
    
Padrísimo! Cuantos ciclos nos podemos ahorrar con esto, no? 



Símbolos
---

Constantes
---

Variables y asignaciones
---

Ejercicios
---
1. Haz un programa que solicite el nombre, primer y segundo apellido e saluda al usuario con su nombre completo.
2. Escribe un programa que solicite el numero favorito del usuario. Luego haz que tu programar multiplique por 10 ese numero y finalmente imprime el resultado sugiriendo al usuario que el nuevo numero es mejor.