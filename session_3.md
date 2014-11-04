Los instrumentos para programar I
===

En esta sesión platicamos sobre las herramientas que nos servirán para mezclar los ingredientes.

Métodos
--
**Métodos conocidos**

Algunos métodos conocidos son **PUTS** y **GETS**, sabemos que cada uno realiza una acción diferente, sin embargo quizás y no sabían que son métodos. Es difícil notarlo porque no se ve la principal característica, el objeto, pero debido a que son métodos de Ruby no es necesario ponerle el objeto ya se están de forma inherente en Ruby.

**La historia detrás del método**

Todos los métodos son la acción de un objeto por lo que llevan nombres de verbos.

Para ser uso de ellos tenemos necesitamos del objeto, checa el siguiente ejemplo:

     "Hola Rubyficadas".reverse
    
"Hola Rubyficadas" -> es el objeto de tipo String

reverse -> es el método

Para invocar el método (hacer uso de el) es por medio del **punto** (.)


**Métodos de String**

Algunos métodos bonitos de String son:
    
- Reverse: invierte el String
- Upcase: convierte todo el String a mayúsculas
- Downcose: convierto todo el String a minúsculas
- Swapcase: convierte las mayúsculas en minúsculas y viceversa
- Capitalize: convierte el primer carácter en mayúsculas y las demás en minúsculas

Escribe en tu programa:

     letters = 'aAbBcCdDeE'
     puts letters.upcase
     puts letters.downcase
     puts letters.swapcase
     puts letters.capitalize
     puts ' a'.capitalize
     puts letters
    
Guarda y corre tu programa ejecutando: ruby elnombrequequieras.**rb**
  
Debes ver como resultado:

     AABBCCDDEE
     aabbccddee
     AaBbCcDdEe
     Aabbccddee
       a
     aAbBcCdDeE
    
Nota que para ' a' el método **capitalize** no funciono, ya que antes de la **a** hay un espacio y capitilize toma el espacio como el primer carácter.

Flujos de control
--
**Métodos de comparación**

Los métodos de comparación los podemos usar entre dos números o dos Strings o simplemente cuando necesitemos comparar dos objetos.

     >  -> mayor que
     < -> menor que
     >= -> mayor o igual
     <= -> menor o igual
     == -> igual
     != -> diferente
    
Cuando comparamos Strings hay que tener en cuenta que la mayúsculas son mayor a las minúsculas.

**OJO**

El resultado de los métodos de comparación son booleanos!

**Branching**
Branching es un concepto muy simple pero poderoso por lo que mejor mostrare como funciona:

Escribe en tu programa:

     puts 'Hola, cual es tu nombre?'
     name = gets.chomp
     puts 'Hola, ' + name + '.'
     if name == 'Viv'
            puts 'Que nombre tan bonito!'
     end
    
Guarda y corre tu programa ejecutando: ruby elnombrequequieras.**rb**
  
Debes ver como resultado:

     Hola, cual es tu nombre?
     Viv
     Hola, Viv.
     Que nombre tan bonito!
    
Eso es branching, si lo que viene después del **if** es verdadero entonces ejecuta lo que esta entre el **if** y **end**. Si lo que viene después del **if** es falso por el momento no pasa nada.

Recuerda indentar el código entre if y end, solo para que sea mas fácil de comprender.

Ahora vamos agregarle a nuestro programa que haga algo cuando la condición después del if es falsa.

Escribe en tu programa:

     puts 'Hola, cual es tu nombre?'
     name = gets.chomp
     puts 'Hola, ' + name + '.'
     if name == 'Viv'
            puts 'Veo cosas increíbles para tu futuro'
       else
            puts 'Tu futuro es ... OMG! Mira la hora!'
            puts 'Necesito irme, perdón'
     end
    
Guarda y corre tu programa ejecutando: ruby elnombrequequieras.**rb**

Debes ver como resultado:

     Soy un adivino del futuro, Dime tu nombre:
     Adela
     Tu future es ... OMG! Mira la hora!
     Necesito irme, perdón

Con el branching podemos crear caminos diferentes por cada nombre, como en el caso de nuestro programa.

Ten encuentra que puedes tener mas **if** de otro if o dentro de un else.

**Looping**
Frecuentemente vas a querer que la computadora realice un proceso una y otra vez, se supone que para eso son buenas. Entonces para que se queden repitiendo un conjunto de instrucciones una y otra vez, vamos a necesitar ciclos.

Cuando le dices a la computadora que quede repitiendo algo, también necesitas decirle cuando quieres que pare. La computadoras nunca se aburren, solo se ciclan, así que sino le dices que pare nunca lo hará. Necesitamos aseguramos que esto no te pase, diciendo a la computadora que repita ciertas partes del programa **mientras** (while) la condición es verdadera. Funciona muy similar al **if**.

Escribe en tu programa:

     command = ''

     while command != 'bye'
            puts command
            command = gets.chomp
     end

     puts 'Come again soon!'
    
Guarda y corre tu programa ejecutando: ruby elnombrequequieras.**rb**

Debes ver como resultado:

     Hello?
     Hello?
     Hi!
     Hi!
     Very nice to meet you.
     Very nice to meet you.
     Oh... how sweet!
     Oh... how sweet!
     bye
     Come again soon!

Eso es un ciclo y te permite hacer todo tipo de cosas interesantes. Pero también pueden ser un gran problema si nos los usas bien. Que pasa si la computadora queda atrababa en un ciclo infinito? Simplmente mantén presionado Ctrl + C.

**Un poco de lógica**
Por ultimo veremos un poco de lógica para hacerte la vida mas fácil.

Los operadores lógicos nos van ayudar para solucionar mas fácilmente nuestros problemas. OR AND y NOT son los operadores.

**Igual echa un vistazo a la tabla de la verdad para que veas como funciona cada uno.**

Escribe en tu programa:
    
     iAmChris  = true
     iAmPurple = false
     iLikeFood = true
     iEatRocks = false

     puts (iAmChris  and iLikeFood)
     puts (iLikeFood and iEatRocks)
     puts (iAmPurple and iLikeFood)
     puts (iAmPurple and iEatRocks)
     puts
     puts (iAmChris  or iLikeFood)
     puts (iLikeFood or iEatRocks)
     puts (iAmPurple or iLikeFood)
     puts (iAmPurple or iEatRocks)
     puts
     puts (not iAmPurple)
     puts (not iAmChris )
    
Guarda y corre tu programa ejecutando: ruby elnombrequequieras.**rb**

Debes ver como resultado:
    
     true
     false
     false
     false

     true
     true
     true
     false

     true
     false
    
Para OR puedes usar ||
Para AND puedes usar &&
Para NOT puedes usar !
    
Retomando nuestro primer ejercicio. Imaginemos que mi mama usa el programa no le dice: "Que bonito nombre!". Creo que esto seria muy triste para ella, así que vamos agregarle un poco de lógica para que cuando mi mama lo use igual le diga que bonito es su nombre.

Escribe en tu programa:

     puts 'Hola, cual es tu nombre?'
     name = gets.chomp
     puts 'Hola, ' + name + '.'
     if name == 'Viv'
        puts 'Que nombre tan bonito!'
     else
     	if name == "Estela"
        	puts 'Que bonito nombre!'
        end
     end
    
Guarda y corre tu programa ejecutando: ruby elnombrequequieras.**rb**

Debes ver como resultado:

     Hola, cual es tu nombre?
     Estela
     Hola, Estela.
     Que bonito nombre!
    
Funciona! Pero no sientes que estamos repitiendo el "Que bonito nombre!"? Mejor vamos aplicar la de DRY (don't repeat yourself)

Escribe en tu programa:

     puts 'Hola, cual es tu nombre?'
     name = gets.chomp
     puts 'Hola, ' + name + '.'
     if name == 'Viv' || name == "Estela"
     	puts 'Que nombre tan bonito!'
     end

Guarda y corre tu programa ejecutando: ruby elnombrequequieras.**rb**

Debes ver como resultado:

     Hola, cual es tu nombre?
     Estela
     Hola, Estela.
     Que bonito nombre!
    
Obtienes el mismo resultado pero tu programa es mas eficiente, simplemente por usar el operador lógico **OR**.

Ahora si vamos a intentar el siguiente ejercicio para ir practicando un poco de lógica ;)

Ejercicios
---

Escribe un programa simulando a tu abuela que casi no oye. Donde lo que sea que digas ella te responde con: HUH?! QUE DICES? HABLA MAS FUERTE! y al menos que tu grites ella te va escuchar y va a responder: NO NO DESDE QUE MURIO TU ABUELO! Si quieres parar de hablar con ella tienes que decirle "ADIOS".

 - Recuerda usar chomp! 'ADIOS' con un Enter no es lo mismo que 'ADIOS' sin uno.

 - Igual intenta pensar que partes de tu programa se tiene que repetir una y otra vez. Quizás eso debe ir en un ciclo
 
 - Puedes incluir un **while** dentro de **if** o dentro de **else** y viceversa puedes incluir un **while** dentro de un **if** o dentro de un **else**.

** Avanzando...  **

Extiende tu programa de la abuela, ahora cada que le digas 'ADIOS' ella hará como la que no te escucha y seguirá hablando y hasta que no le digas 3 veces 'ADIOS' en una sola linea, entenderá.