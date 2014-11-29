#Los instrumentos para programar II

Esta sesión platicamos sobre arreglos e iteradores.

##Arreglos

Imaginemos que tenemos que escribir un programa que nos permita ingresar todas las palabras que queramos (una por linea, continuando hasta que presionemos Enter en una línea en blanco), y luego que repita las palabras en orden alfabético.

Como le haríamos? Guardaríamos cada una de las palabras ingresadas en variables separadas? Pero no sabemos cuantas palabras va ingresar el usuario :(

No creo que podamos hacerlo de esa forma, quizás necesitamos algo donde podamos guardar todas la palabras ingresadas, o sea tenemos que ponerlas como en una lista entonces necesitamos arreglos.

Un arreglo es solo una lista en tu computadora. Cada celda de la lista actua como una variable.

Juguemos un poco:

     []                                        #Este es un arreglo vacío
     [5]                                        #Este es un arreglo con un elemento, el numero 5
     ['Hola', 'Adios']                    #Este es un arreglo con dos Strings     

     sabor = 'vainilla'             # Esto no es un arreglo!
     [89.9, sabor, [true, false]]      #Este es un arreglo con 3 elementos el ultimo es un arreglo [true,false]
     
Recuerda, variables (como "sabor") no son objetos, por lo que en nuestro ultimo arreglo esta realmente apuntando a un float, a un String y a un Array. Incluso si le decimos a "sabor" que tome otro valor, eso no cambiaría el valor en el arreglo.

Para ayudarnos a buscar un elemento en particular del arreglo, cada celda tiene un numero index. Programadores (y, la mayoría de matemáticos) empiezan a contar desde cero, aunque, entonces la primera celda del arreglo es la celda cero. Aquí puede ven como hacer referencia a objetos en un array:

     nombres = ['Erika', 'Lucy', 'Sol']

     puts nombres
     puts nombres[0]
     puts nombres[1]
     puts nombres[2]
     puts nombres[3]                     #Esta queda fuera del rango del arreglo
     
Deben de ver algo así:

     Erika
     Lucy
     Sol
     Erika
     Lucy
     Sol
     
Vemos que "puts nombres" imprime cada elemento del arreglo. Luego usamos "puts nombres[0]" para imprimir el primer nombre del arreglo, y puts nombres[1] para imprimir el segundo... Se que puede ser un poco confuso al inicio pero solo es cuestión que comiences a contar desde 0, y no usar "primero" y "segundo".

Al final, pusimos "puts nombres[3]" solo para ver que pasaba. Estabas esperando un error? A veces cuando haces una pregunta, esta no tiene sentido (al menos en la computadoras); y cuando obtienes un error. A veces, como sea, puedes hacer una pregunta y la respuesta es nada. Que hay en la celda 3? Nada. Que es nombres[3]? nil: es la forma de Ruby para decirnos que la respuesta es nada. **nil** es un objeto especial que básicamente significa "ningún otro objeto". Y cuando haces "puts nil" no imprime nada (solo una nueva línea).

###Método "each"

each nos permite hacer algo (lo que sea que queramos) a cada objeto del arreglo. Entonces si queremos algo bonito sobre algún lenguaje, hacemos algo como esto:

     lenguajes = ['Ingles', 'Aleman', 'Ruby']

     lenguajes.each do |leng|
            puts 'Amo el ' + leng + '!'
            puts 'tu no?'
     end

     puts 'Que dices de Java?'
     puts '...'

Como resultado debemos ver:

     Amo el Ingles!
     tu no?
     Amo el Aleman!
     tu no?
     Amo el Ruby!
     tu no?
     Que dices de Java?
     ...
     
Que acaba de pasar? Pues fuimos a través que cada objeto del arreglo sin usar ningún numero, genial no? Si traducimos este programa al español se lee así:

     Para cada objeto de lenguajes, apunta la variable leng al objeto y luego haz todo lo que yo diga hasta que termines con todos los objetos del arreglo.
     
Dirás que esto se parece mucho a los ciclos que hemos visto anteriormente, y si son similares. Sin embargo tienes que notar que **while**, **if** and **else** no son métodos,y son fundamentales para Ruby así como "="" y los paréntesis. Son los signos de puntuación de Ruby ;)

Métodos como each que actúan como cliclos se les llama iteradores.

Hay otro iterador muy chido, pero no es un método de "Array", es de "Integer":

     3.times do
            puts 'Hip-Hip-Hooray!'
     end
     
Como resultado debes de ver:

     Hip-Hip-Hooray!
     Hip-Hip-Hooray!
     Hip-Hip-Hooray!
     
###Otros metodos de arreglos!

Ya vimos como funciona el each, pero Array tiene muchisisimos mas métodos (así como String). De hecho coinciden en algunos y funcionan de la misma forma: length, reverse,  +, y *, solo que estos trabajan con las celdas del arreglo en vez de los caracteres del String. Otros como **last** o **join** son específicos de Array. Revisa la [documentación](http://www.ruby-doc.org/core-2.1.5/Array.html) de Ruby para que descubras que otros métodos existen.

Primero vamos a ver como funcionan **to_s** y **join**. **join** funciona similiar a **to_s** pero este agrega un String entre cada objeto del array. Veamos:

     postres = ['brownie', 'cup cakes', 'bizcocho ingles']

     puts postres
     puts
     puts postres
     puts
     puts postres(', ')
     puts
     puts postres('  :)  ') + '  8)'

     200.times do
            puts []
     end 
     
Como resultado debemos ver:
     
     brownie
     cup cakes
     bizcocho ingles
     
     ["brownie","cup cakes","bizcocho ingles"]
     
     brownie, cup cakes, bizcocho ingles
     
     brownie :) cup cakes :) bizcocho ingles 8)

Como puedes ver "puts" trata diferente a los arreglos que a los objetos: este hace **puts** a cada objeto del arreglo. Por eso al final del ejemplo donde pusimos 200 veces puts a un arreglo vacío no imprimo nada, el arreglo no apuntaba a nada así que no había nada que imprimir. 

Ahora veamos **push**, **pop** y **last**. Los metodos de **push** y **pop** son como polos opuestos, como + y -. **push** añade un objeto al final del arreglo y **pop** elimina el ultimo objeto del array. **last** es similar a **pop** ahi te dice que hay al final del arreglo, pero no elimina el objeto.

     favorites = []
     favorites.push 'raindrops on roses'
     favorites.push 'whiskey on kittens'

     puts favorites[0]
     puts favorites.last
     puts favorites.length

     puts favorites.pop
     puts favorites
     puts favorites.length
     
Debes ver como resultado:

     raindrops on roses
     whiskey on kittens
     2
     whiskey on kittens
     raindrops on roses
     1
     
##Ejercicios

Escribe un programa que le permita al usuario ingresar cuantas palabras quiera y solo parar de pedir palabras cuando ingrese un linea en blanco. Luego muestra todas las palabras en orden alfabético. Tip: revisa el método **sort** ;)


