#Objetos de la vida real en código

En esta sesión recordamos lo que son los objetos y aprendemos a crearlos en Ruby.

##Objetos

Los objetos son entidades que tienen un determinado estado, comportamiento (método) e identidad:

- El estado está compuesto de datos o informaciones; serán uno o varios atributos a los que se habrán asignado unos valores concretos (datos).
- El comportamiento está definido por los métodos o mensajes a los que sabe responder dicho objeto, es decir, qué operaciones se pueden realizar con él.
- La identidad es una propiedad de un objeto que lo diferencia del resto; dicho con otras palabras, es su identificador (concepto análogo al de identificador de una variable o una constante).

Un objeto contiene toda la información que permite definirlo e identificarlo frente a otros objetos pertenecientes a otras clases e incluso frente a objetos de una misma clase, al poder tener valores bien diferenciados en sus atributos. A su vez, los objetos disponen de mecanismos de interacción llamados métodos, que favorecen la comunicación entre ellos. Esta comunicación favorece a su vez el cambio de estado en los propios objetos. Esta característica lleva a tratarlos como unidades indivisibles, en las que no se separa el estado y el comportamiento.

##Métodos

Los métodos son como una envoltura de regalo, los cuales nos permiten guardar dentro de ellos fragmentos de código y así como vimos con los ciclos y los iteradores, nos permiten hacer la misma cosa una y otra vez. Muchas veces queremos hacer lo mismo cierto numero de veces, pero en diferentes partes del programa. Imaginemos que queremos escribir un programa para hacer un cuestionario:

     puts 'Hello, and thank you for taking the time to'
     puts 'help me with this experiment.  My experiment'
     puts 'has to do with the way people feel about'
     puts 'Mexican food.  Just think about Mexican food'
     puts 'and try to answer every question honestly,'
     puts 'with either a "yes" or a "no".  My experiment'
     puts 'has nothing to do with bed-wetting.'
     puts

     # We ask these questions, but we ignore their answers.

     goodAnswer = false
     while (not goodAnswer)
            puts 'Do you like eating tacos?'
            answer = gets.chomp.downcase
            if (answer == 'yes' or answer == 'no')
              goodAnswer = true
            else
              puts 'Please answer "yes" or "no".'
            end
     end

     goodAnswer = false
     while (not goodAnswer)
            puts 'Do you like eating burritos?'
            answer = gets.chomp.downcase
            if (answer == 'yes' or answer == 'no')
              goodAnswer = true
            else
              puts 'Please answer "yes" or "no".'
            end
     end

     # We pay attention to *this* answer, though.
     goodAnswer = false
     while (not goodAnswer)
            puts 'Do you wet the bed?'
            answer = gets.chomp.downcase
            if (answer == 'yes' or answer == 'no')
              goodAnswer = true
              if answer == 'yes'
                     wetsBed = true
              else
                     wetsBed = false
              end
            else
              puts 'Please answer "yes" or "no".'
            end
     end

     goodAnswer = false
     while (not goodAnswer)
            puts 'Do you like eating chimichangas?'
            answer = gets.chomp.downcase
            if (answer == 'yes' or answer == 'no')
              goodAnswer = true
            else
              puts 'Please answer "yes" or "no".'
            end
     end

     puts 'Just a few more questions...'

     goodAnswer = false
     while (not goodAnswer)
            puts 'Do you like eating sopapillas?'
            answer = gets.chomp.downcase
            if (answer == 'yes' or answer == 'no')
              goodAnswer = true
            else
              puts 'Please answer "yes" or "no".'
            end
     end

     # Ask lots of other questions about Mexican food.

     puts
     puts 'DEBRIEFING:'
     puts 'Thank you for taking the time to help with'
     puts 'this experiment.  In fact, this experiment'
     puts 'has nothing to do with Mexican food.  It is'
     puts 'an experiment about bed-wetting.  The Mexican'
     puts 'food was just there to catch you off guard'
     puts 'in the hopes that you would answer more'
     puts 'honestly.  Thanks again.'
     puts
     puts wetsBed

Como resultado veras:

     Hello, and thank you for taking the time to
     help me with this experiment.  My experiment
     has to do with the way people feel about
     Mexican food.  Just think about Mexican food
     and try to answer every question honestly,
     with either a "yes" or a "no".  My experiment
     has nothing to do with bed-wetting.

     Do you like eating tacos?
     yes
     Do you like eating burritos?
     yes
     Do you wet the bed?
     no way!
     Please answer "yes" or "no".
     Do you wet the bed?
     NO
     Do you like eating chimichangas?
     yes
     Just a few more questions...
     Do you like eating sopapillas?
     yes

     DEBRIEFING:
     Thank you for taking the time to help with
     this experiment.  In fact, this experiment
     has nothing to do with Mexican food.  It is
     an experiment about bed-wetting.  The Mexican
     food was just there to catch you off guard
     in the hopes that you would answer more
     honestly.  Thanks again.

     false
     
En fin, que programa tan largo y repetitivo. Repetir es algo malo porque no ayuda en el rendimiento de la computadora que esta ejecutando el código.


###Definiendo métodos

Para definir un metodo usamos **def** seguido del nombre del método y luego de los parametros de este. Algo así:

     def rodar numero_de_veces
          puts "... || \\ // || ..." * numero_de_veces
     end
     
**numero_de_veces** es un parámetro para nuestro método **rodar**, esto nos sirve para indicarle cuantas veces queremos que ruede nuestro perro.

Como ya habíamos visto en sesión anteriores, los objetos son como pronombres, los métodos como verbos, entonces podemos ver a los parámetros como adverbios (como en nuestro método rodar el parámetros numero_de_veces nos ayudaba para hacer rodar las veces que queramos a nuestro objeto perro). A los método podemos enviarle como parámetro cualquier tipo de variable y cuantas queramos.

###Variables locales
En el siguiente ejemplo hay dos variables:

     def doubleThis num
            numTimes2 = num*2
            puts num.to_s+' doubled is '+numTimes2.to_s
     end

     doubleThis 44  

Las variables num y numTimes2 que están dentro del método **doublethis**  son variables locales, es decir solo van a vivir dentro de ese método y no van funcionar fuera de el.

Si intentamos algo como:

     def doubleThis num
            numTimes2 = num*2
            puts num.to_s+' doubled is '+numTimes2.to_s
     end

     doubleThis 44
     puts numTimes2.to_s
     
Vamos a tener un error en la ultima linea porque estamos intentando utilizar **numTimes2** cuando este solo funciona dentro del método **doubleThis**.

###Regresando valores

Ahora la pregunta es, que pasaría si necesito una variable que esta dentro de un método? Afortunadamente existe una forma para que el método nos regrese una variable cuanto este termina. OJO la variable que regresa puede ser de cualquier tipo de dato (String, Integer, Boolean, Array ... etc).

Retomando el ejemplo anterior:

     def doubleThis num
            numTimes2 = num*2
            puts num.to_s+' doubled is '+numTimes2.to_s
            numTimes2                          #Lo que esta regresando el método     end

     double = doubleThis 44
     puts double.to_s
     
El método **doubleThis** esta regresando la variable **numTimes2**, significa que si queremos hacer uso simplemente el valor de numTimes2 podemos hacerlo fuera del método sin problema.                    
     
Algo importante que hay que notar aquí, es que no es lo mismo que un método regrese un valor a que un método imprima algo en consola (recuerda solo **puts** puede hacer eso). Que un método regrese algo solo esta dejando disponible la variable fuera del método.

##Clases

Hasta aquí hemos visto diferente tipos de clases y objetos: strings, integers, floats, arrays, y algunos casos especiales como: true, false y nil. En Ruby la clases siempre van capitalizadas: String, Integer, Array, Float. 

###Creando clases

Hemos visto diferentes clases, en Ruby es muy fácil crear nuevas clases. Afortunadamente es igual de fácil crear una como extender las que ya existen. Vamos a crear una nueva clase en Ruby:

     class Perro
          def rodar
               puts "... || \\ // || ..."
          end
     end
     
     perros = [Perro.new, Perro.new]
     
     perros.each do |perro|
           perro.rodar
     end
     
Para definir una clase necesitamos de la palabra reservada **class** seguido del nombre de la clase, en este caso "Perro".
     
Luego podemos ver como ruedan nuestros perros:

     ... || \ // || ...
     ... || \ // || ...
     
Listo, creamos nuestra primera clase!

###Instanceando objetos

Ahora vamos hacer nacer perros, la clase en si sola únicamente modela la idea de un perro, por lo que para hacerlos nacer necesitamos crear una nueva instancia de esa clase:

     perro1 = Perro.new
     
La estructura para instancear una clase es: nombre de la clase, en este caso "Perro" e invocar el métodos "new" y obtenemos el "perro1" que tiene la habilidad de rodar.

Ahora podemos modificar la genética de nuestro perro para que siempre tenga las mismas características simplemente definiendo un método con el nombre de "initialize" (si esto fuera Java, es el constructor)

     class Perro

          def initialize(raza, color, peso)
               @raza = "Bulldog francés"
               @color = "blanco"
               @peso = 10
               ladra
          end

          def rueda (numero_de_veces)
               puts "... || \\ // || ... \n" * numero_de_veces
          end

          def ladra
               puts "guaf guaf" * @peso
          end

     end
     
Si volvemos a crear una instancia de Perro ahora por default va a ser un bulldog francés blanco de 10 kilos que ladra inmediatamente después de que nace.

No se preocupen sino les gustan los perros con estas características, también hay forma de poder crearlos a nuestro gusto.

     class Perro

          def initialize(raza, color, peso)
               @raza = raza
               @color = color
               @peso = peso
               ladre
          end

          def ruede (numero_de_veces)
               nombres = ['Kary',"Rosa",'Lid']
               puts "... || \\ // || ... \n" * numero_de_veces
               nombres
          end

          def ladre
               puts "guaf guaf" * @peso
          end
          
          def raza
               @raza
          end

     end

Y así podemos crear un perro con otras características:

     perro2 = Perro.new "Chihuahua","negro",3
     
Sin embargo este seguirá ladrando inmediatamente después de que nazca.

###Variables globales

Dentro de nuestro método "initialize" definimos unas variables con "@", es significa que esa variable puede ser utilizada en cualquier momento dentro de la clase. Así podemos hacer uso de la variable "peso" dentro del método "ladre". Si mas adelante necesitamos saber de que raza es el perro que creamos, tenemos que crear un métodos que nos regrese ese valor para que podamos hacer uso de esa variable, tal y como lo estamos haciendo en el ultimo método llamado "raza".
  

