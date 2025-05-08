
# 1. CONDICIONALES  


<h2>if</h2>

Una sentencia condicional nos permite establecer si algo es verdadero o falso.
El condicional se utiliza cuando quieres que se cumpla un código con una condición específica y que se ejecute si esto es cierto y que se ejecute otro código cuando la condición no se cumple.  

Nos permite manejar distintas decisiones y controlar el flujo de los programas.  

Utilizamos "if" para indicar que si lo que pongo en el código es verdadero quiero que lo ejecute, si es falso, no quiero que lo  ejecute.

~~~
    a=1
    b=2
    if b>a :
        print('b es mayor que a ')
~~~  

Es el código que se ejecutará unicamente si la condición es verdadera.
Si hubiese sido mentira( a>b) la instrucción no se ejecuta.

Cuando utilizamos "if" siempre tiene que terminar la sentencia en dos puntos :
y el bolque de código debe estar anidado. 

Es posible que no sólo queramos hacer algo si una determinada condición se cumple, sino que además queramos hacer algo de lo contrario. En este caso se utiliza el condicional "else". Si usamos "if" y es falso entonces podemos usar otra condición 'else'.

<h2>else</h2>


Si tenemos un código en el que "if" no se cumple entonces podemos utilizar la sentencia "else" asi das otra condición.  


~~~
    edad = 18
    if edad >= 18:
        print("Puedes conducir")
    else:
        print("No puedes conducir")
~~~  



<h2>elif</h2>

Nos permite concatenar condiciones adicionales. Primero mira las dos primeras condiones. Si la primera es verdadera, sino mira la segunda. y si ambas condiciones son falsas, se ejecutará.

 ~~~

age= 19
if age < 18:
    print('no puedes conducir')
elif age >21:
    print ('puedes conducir y alquilar un coche')
else:
    print('puedes conducir')  
~~~


# 2.BLUCLES EN PYTHON  ¿Por qué son útiles?

Los bucles son una herramienta para alterar el flujo normal de un programa. Nos permiten repetir una porción de código tantas veces como queramos.

Hay dos tipos de bucles *for...in* y *while*. Ambos se pueden usar para colecciones, rangos de números, listas, tuplas o diccionarios.
ES imprescindible marcar un inicio y señalar las condiciones verdaderas o falsas. La iteración sucede cuando es verdadera y para cuando es falsa.
Con for se produce un número limitado de veces, con while es indefinido hasta que cambia la condición.

<h2>Bucle for</h2>

Con el bucle for se sabe cuántas veces se va a repetir el programa. 
La iteración depende de la cantidad de objetos recogidos en las líneas de códigos y que finalizará cuando se cumplen todos los valores. Se aplica cuando el bloque a iterar tiene un número definido de elementos.

    for <elem> in <variable>:
     bloque de código

Sirven por ejemplo para detectar en una lista elementos con unas condiciones verdaderas.

<h3>Bucles en listas</h3>

        PLayers = ['Pedri', 'Gabi', 'Ferrán']
        player= 'Fermín'
        for player in players:
            print(player)

Después de colocar el bucle en Python siempre hay que poner dos puntos y la siguiente línea de código siempre en sangría. 

Nos imprimirá toda la lista.
    Pedri
    Gabi
    Ferrán
En esta lista como podemos ver no aparece 'Fermín' porque no estaba definido dentro de la lista.

En este ejemplo "players" es la variable que hay que mantener con el nombre idéntico. Es la colección con la que vamos a trabajar.
La primera variable "player" puede tener cualquier nombre. Puedes poner en singular la variable principal o simplemente decir "x". Lo que representa esto es que cada vez que este bucle progresa y lo itera, va a cambiar. La primera vez va a cambiarlo por jugador "Pedri", luego "Gabi" y luego "Ferrán". Así hasta acabar con la colección de elementos de la lista.

<h3>Bucles en tuplas</h3>

Con una tupla el comportamiento es igual en cuanto a bucles.

    players=('Pedri', 'Gabi', 'Ferrán')
    for x in players:
        print(x)

Esto nos devuelve la tupla de la misma forma que si hubieramos usado una lista.
    Pedri
    Gabi
    Ferrán

<h3>Bucles en diccionario</h3>

La sintaxis es similar para usar los blucles, aunque ahora no trabajamos con un único elemento, necesitamos coger la clave y el valor. Despues de pasar el bucle for hay que darle dos elementos. Si antes teníamos jugador, ahora le damos tambien un valor de la posición en la que juega cada uno.

Luego tenemos que crear una función *item* y como cualquier función debe llevar paréntesis al final() y después dos puntos : .
La función item nos va a permitir crear una visita dentro del diccionario. Nos da acceso a todos los elementos y por eso podemos pasar dos variables.

    for posición, jugador in jugadores.item():

~~~
    jugadores = {
        'medio' : 'Pedri',
        'lateral' : 'Gabi',
        'central' : 'Ferrán'
    }
    for posición, jugador in jugadores.items():
        print('Posición', posición)
        print('Nombre Jugador', jugador)

~~~  


Nuestro primer item que es 'Pedri' va a ser asignado con la posición 'medio'.
La variable posición es igual a la clave y jugador es igual al valor.
La importancia de la sangría es clave después de dos puntos ':' en Python. Por eso print en estos casos tiene que ir con sangría. Siempre pueden ser de dos espacios o cuatro.
Así, esto nos devolvería lo siguiente:  

~~~
    Posición medio
    Nombre Jugador Pedri
    Posición lateral
    Nombre Jugador Gabi
    Posición central
    Nombre Jugador Ferrán
~~~  


Podemos utilizar *for...in* para fusionar varias listas.

Por ejemplo: tenemos una lista de clientes_antiguos y otra de clientes_nuevos y queremos juntar ambas. Pero no queremos que nos dé dos listas juntas, sino que queremos que sean cadenas juntas.  


~~~  
    clientes_antiguos = ['Alba','Ibai']
    clientes_nuevos = ['Raquel', 'Zuri']
    for clientes_antiguos in clientes_antiguos:
        clientes_nuevos.append(clientes_antiguos)
        print(clientes_nuevos)
~~~  

La función *append* añadida a clientes_nuevos. Esta función vale para todo tipo de datos en listas.  
El bucle for lo que hace es iterar nuestra lista de clientes_antiguos y con cada bucle introducimos los datos de la siguiente lista que es clientes_nuevos. Iteramos esta última lista y tratamos sus elementos como cadenas normales.  

Los bucles pueden ir desde el principio de un programa hasta el final. Pero a veces puedes querer parar o alterar el comportamineto de una lista en algún momento determinado.  
En este caso tenemos dos operadores de control de flujo: continue y break.
Quiero que en una lista de nombres cuando llegue el bucle a un nombre concreto cambie su comportamiento. Sólo quiero que haga determinada acción al ver ese nombre.  

~~~ 
    nombres= ['Ibai', 'Alba', 'Raquel', 'Zuri']
    for nombre in nombres:
        if nombre=='Raquel':
            print (f' Lo siento, {nombre}, no estas autorizado')
            continue
        else:
            print(f' {nombre} estas autorizado')
~~~  


Si encuentra la condición y es verdadera, es decir, si encuentra a un usuario con nombre Raquel, camnbia el comportamiento. Pero lo más importante es que sigue adelante y continúa analizando el resto de elementos. *Continue* le dice al programa que tiene que continuar con el bucle. Sigue itinerando sin parar una vez que encuentra lo que busca. Hace bucle en todos los nombres de la lista.  

! [Blucle continue] (Users\IBAI\OneDrive\Escritorio\checkpoint5\3.png · Untraked)

<img src= "Users\IBAI\OneDrive\Escritorio\checkpoint5\images.md\3.png"alt="Bucle continue" width="500">  


~~~
    Ibai estas autorizado
    Alba estas autorizado
    Lo siento, Raquel, no estas autorizado
    Zuri estas autorizado
~~~  

Esto es lo opuesto a lo que haría *break*. Este operador busca y destruye. Mira la lista de nombres y si encuentra el valor que hemos dado no le importa lo demás. Cuando encuentra la condición acaba.  

~~~
    for nombre in nombres:
        if nombre == 'Raquel':
            print (f' {nombre} se encuentra en index {nombres.index (nombre)}')
            break
        print(nombre)
~~~  

En la misma línea de la declaración *print* pongo *break* porque tienen que estar anidados dentro del condicional *if*. El último *print* sale fuera porque cualquier cosa despúes de *break* no pasará anidado dentro del bloque de código.  


~~~
    Ibai
    Alba
    Raquel se encuentra en index 2
~~~  

El programa sólo sirve para decirnos en qué índice se encuentra nuestro elemento. La clave aquí es que todo lo que va en la lista después de nuestro valor, no estrará incluído. *Break* te saca de la condicional, mira arriba, atraviesa la cadena y cuando encuentra lo que está en el bucle, le dice a Python que ya lo ha encontrado y sale del bucle. 



<h2>Bucle while</h2>

Un *bucle while* es una estructura de control de flujo en programación que permite ejecutar repetidamente un bloque de código mientras una condición específica se determina como verdadera. La condición se evalúa al principio de cada iteración del bucle, y el bloque de código se ejecuta mientras la condición siga siendo verdadera. Si la condición es falsa desde el principio, el bloque de código dentro del while nunca se ejecutará.

En el *bucle while* no se conoce el número de repeticiones que quieres en un programa y puede repetirse indefinidamente siempre que la secuencia sea verdadera.
Hay que especificar cuando tiene que detenerse porque puede convertirse en un bucle infinito y el programa no se va a detener nunca hasta que cambie la condición. Puede hacer que un programa se bloquée.  


Un valor centinela es el término para definir cuando debe pararse este bucle.

El *bucle while* es útil cuando no se conoce de antemano cuántas veces se necesita ejecutar el código, sino que la ejecución depende de una condición. 
Se puede usar para pedir a un usuario que ingrese datos válidos, repitiendo la solicitud hasta que sean correctos. Si introduce un dato erróneo entonces el programa se detiene.  

~~~
    contador= 0
    while contador <5:
        print(contador)
        contador += 1  

    print('Bucle terminado')  
~~~  


En este ejemplo el *bucle while* se ejecutará 5 veces. Desde el 0 al 4.
La condición es que el contador sea menor que 5 y el bucle continuará ejecutándose hasta que esto deje de ser cierto. Mientras la variable contador sea menor que 5, el código dentro del bloque se ejecuta.  


Imprimimos el valor que hemos dado al principio (contador=0) y luego tenemos que ir incrementando ese contador en 1. Este paso es importante para que la condición se vuelva falsa en algún momento y el bucle se detenga. Cuando esto suceda mostramos *Bucle terminado*.

No es tan intuitivo como el *bucle for*. Se usa bastante menos.  

Para adivinar un deteminado número o en juegos de adivinanzas es una buena opción este bucle. En estos casos no se sabe cuántas veces se debe repetir el programa.
Pides al usuario que adivine un número y hasta que acierte,el programa seguirá ejecutándose. (No podríamos usar el bucle *for in* porque no sabemos cuándo va a acertar).  

~~~
    import randow
    numero_secreto = random.randint(1, 10)
    intento = 0

    print("¡Adivina el número secreto entre 1 y 10!")

    while intento != numero_secreto:
        try:
            intento = int(input("Introduce tu intento: "))
            if intento < numero_secreto:
                print("Demasiado bajo. ¡Intenta de nuevo!")
            elif intento > numero_secreto:
                print("Demasiado alto. ¡Intenta de nuevo!")
            else:
                print(f"¡Felicidades! ¡Adivinaste el número secreto: {numero_secreto}!")
    print("Juego terminado.")
~~~

Se importa primero el módulo randow para generar un número secreto aleatorio y queremos que ese número entero aleatorio se encuentre entre el 1 y el 10. Ambos inclusive.
El primer intento damos un número que sea falso para que el bucle while se ejecute al menos una vez. Y asi seguirá ejecutándose hasta que el usuario acierte el número secreto.  

Los **bucles son útiles** porque nos permiten ejecutar repetidamente un bloque de código sin tener que escribirlo varias veces.
Si necesitas realizar la misma taréa múltiples veces pero con ligeras variaciones, puedes ahorrar tiempo y reduces la probabilidad de errores. El código se vuelve más compacto y fácil de entender.
Iterar sobre una secuencia ya sea lista, tupla o diccionario significa recorrer cada elemento uno por uno. Asi los bucles consiguen crear programas dinámicos capaces de realizar tareas repetitivas de forma eficiente.  



# 3. LISTA POR COMPRESIÓN EN PYTHON


Es una forma concisa de crear listas en Python.
Una lista por compresión es una construcción sintáctica elegante y concisa que permite crear nuevas listas basadas en listas existentes de una manera más clara y a menudo más eficiente que utilizando bucles for tradicionales.  

Una lista por comprensión ofrece una forma abreviada de poner una expresión a cada elemento de una secuencia (como una lista, tupla o rango) y, opcionalmente, filtrar los elementos que cumplen una determinada condición, todo dentro de una única línea de código.


La compresión de listas es una forma eficiente de iterar una lista con pocas líneas de código. En programas grandes esto es fundamental, ocupar poco espacio y menos código. Principalmente para evitar errores.

~~~
    my_list = ['good', 'play', 'futbol']
    result = [word[0], for word in my_list]
    print(result)
~~~  

Esto nos daría como resultado la primera letra de cada palabra ['g', 'p', 'f']

~~~
    my_list = [1,2,3,4,5]
    new_list = [item *2 for item in my_list]
    print(new_list)
~~~  

Nos daría los elementos de "my_list" multiplicados por dos [2, 4, 6, 8, 10]    

~~~
    nombres = ['Alicia', 'Bob', 'Charlie', 'David']
    iniciales = [nombre[0] for nombre in nombres]
    print(iniciales)  
~~~  


 Nos devuelve la primera letra de cada nombre: ['A', 'B', 'C', 'D']


# 4. ARGUMENTO EN PYTHON

En Python, un argumento es un valor o expresión que se pasa a una función cuando se la llama. Estos argumentos se utilizan para proporcionar a la función la información que necesita para realizar su tarea. Los argumentos pueden ser de tipo posicional (se pasan por posición) o de tipo nombre (se pasan con un nombre).  



<h2> Argumentos Posicionales</h2>

Cada vez que pasamos valores de argumento a funciones usamos lo que se llama argumentos posicionales. Según el sitio o el valor que le quieras dar. Deben incluírse en la posición u orden adeciuados. El primer argumento posicional siempre debe aparecer el primero a la hora de llamar a la función. El segundo en segundo lugar y así sucesivamente. 

~~~
    def suma(a, b): 
        return a + b 
    print(suma(3, 5)) 
~~~  

En este caso, 3 y 5 son argumentos posicionales que se pasan a los parámetros a y b, respectivamente.  

Esto está bien para funciones pequeñas, en grandes los argumentos posicionales pueden generar confusión. 

~~~
    def nombre_completo('nombre', 'apellido'):
        print(f' {nombre}{apellido})
    nombre_completo ('Alba', 'Gonzalez')
~~~  

Alba pasará siempre como primer argumento ya que lo hemos colocado como primer elemento. González será el último valor.  
Todo se basa en la posición de los argumentos.




<h2> Argumentos de nombre</h2>


Son aquellos que se pasan a la función especificando el nombre del parámetro al que se asignan.  

~~~
    def suma(a, b):
        return a + b:
    print(suma(b=5, a=3))
~~~  


En este caso, b=5 y a=3 son argumentos de nombre.
El orden en que se pasan los argumentos de nombre no importa.  

~~~
    def nombre_completo('nombre', 'apellido'):
        print (f'{nombre}{apellido})
    nombre_completo(nombre='Alba', apellido= 'González')
~~~  

Aquí los argumentos con nombre nos permiten ser mucho más explícitos. En lugar de simplemente pasar una cadena pasamos el nombre. El programa examina la llamada a función y verá que hemos configurado argumentos con nombre. Primero coge el primer elemento y así sucesivamente. Pero no importa la posición en la que están colocados los argumentos.
Además, Python permite utilizar indistintamente argumentos de nombre o posicionales en las funciones como tú desees. Puedes intercambiarlos.  


Lo ideal es usar argumentos con nombre cuando hay más de dos argumentos, para evitar problemas de colocar los valores en el orden incorrecto o llamarlos con un nombre distinto.  

<h2> Argumento con valor por defecto</h2>

Son argumentos que se les asigna un valor en el código de la función, pero también se pueden sobrescribir en tiempo de ejecucuón.  

~~~ 
    def multiplicación (a, b ***=*** 6):
        return a * b

    print1= multiplicación (2)
    print2= multiplicación (2, 5)
~~~  

El primer resultado nos daría 12 (2 por 6, mantenemos el valor que hemos puesto arriba) y el segundo 10 (2 por 5, hemos sobrescrito el valor de b).  
Se pueden definir valores por defecto para los argumentos en caso de no ser enviados en la función.  

<h2>Argumentos con palabras clave</h2>

Se definen sin más mediante la palabra clave seguida del signo igual y su valor correspondiente. Hacen nuestro código más legible y adaptable. Porque al ver la llamada a la función, es inmediatamente obvio qué valor se está asignando a cada parámetro. Esto hace que el código sea más fácil de entender. No tienes que poner los elementos en orden.
Puedes pasarlos en cualquier orden, siempre y cuando especifiques el nombre del parámetro.  

~~~
    def despedir(nombre, despedida):
        print(f' {nombre} {despedida}')
    despedir(nombre="Ibai", despedida="adios")
    despedir(despedida= 'Adios' , nombre= 'Ibai')
~~~  

  

# 5 . FUNCIÓN LAMBDA EN PYTHON  


La función *Lambda* es una herramienta que nos permite empaquetar una función y luego introducirla en otras funciones. Son muy móviles y fáciles de usar.  

Es muy similar a una variable que se puede introducir en lugar de un valor básico como una cadena o un diccionario. 
Una variable almacena datos una función lambda (o cualquier función) almacena código.
Nos permite empaquetar un proceso.
Una *lambda* siempre devuelve un valor.  

Su sintaxis es:
    argumentos lambda: expresión

El valor de retorno de la función lambda es el valor al que se evalua esta expresión.  

~~~
    nombre_completo= lambda first,last: f'{first} {last}'
    nombre= nombre_completo ('Alba', 'Gonzalez')
    print(nombre)
~~~  


Devolvemos un valor de nombre completo y lo almacenamos en la variable nombre_completo.
Después de llamar a lambda escribimos una serie de argumentos, en este caso, nombre y apellido. Lo que vaya dentro de las comillas es lo que devolverá *lambda*.
En este caso hemos formateado una cadena que toma la variable de nombre y apellido.
Después hay que imprimirlo porque *lambda* sólo devuelve valor. 
Nos daría como resultado: Alba González.  

Las funciones lambda son anónimas, no tienen un nombre formal como las funciones 'def'. Generalmente se asignan a una variable para poder llamarlas.
La sintáxis es concisa mucho más que en las funciones *def*.
Están creadas para utilizarse en expresiones simples que se puedan hacer en una sola línea.
El cuerpo de la función lambda debe ser una única expresión. No pueden contener múltiples referencias o bloques de código complejos.
Son adecuadas para operaciones sencillas. Para lógica compleja las funciones *def* son más legibles y adecuadas.

La función lambda suele utilizarse para lo siguiente: como argumento que son pasados a otras funciones de orden superior, o para construir el resultado de una función de orden superior que necesita retornar una función.

~~~
    es_par= lambda_numero = numero %2 ==0
    print(f'(numero 10 es par?))

~~~  
    

Las funciones lambda pueden aceptar cero o más argumentos, pero **sólo una expresión**.  


~~~
    f= lambda x: x*x
    f(5)
    
~~~  

Nos daría como resultado 25.  

Ahora pasamos dos argumentos: 

~~~
    f= lambda x, y : x* y
    f(5,2)
~~~  


Nos daría como resultado 10.




# 6 . PAQUETE PIP      


Un paquete es una colección de archivos, módulos y dependencias relacionados que pueden utilizarse repetidamente en diferentes aplicaciones y problemas.
Pip es un gestor de paquetes estándar en Python.  

Pip es un sistema de gestión de paquetes para Python. Su nombre proviene de *Pip Installs Packages* o *Pip Instala Paquetes* en español.

Con pip, podemos instalar, actualizar y desinstalar paquetes de Python en un ordenador de manera sencilla.

Los paquetes son colecciones de módulos y funciones que pueden ser distribuidos y utilizados por otros programadores.  


Hay que instalarlo en nuestro ordenador para poder utilizarlo. Simplemente tienes que utilizar pip install. Es el programa de instalación más usado.

~~~
    pip install nombre-paquete
~~~  

Para desintalarlo sólo hay que usar  


~~~
    pip uninstall nombre-paquete
~~~  


Hay paquetes que están ya incorporados en Python o que podemos crear nosotros mismos. Con pip podemos incorporar módulos creados por otros desarrolladores y usarlos en nuestros propios programas.  

Una vez instalado pip podemos gestionar paquetes diferentes.

Sólo hay que llamar a pip seguido por install y el nombre del paquete.

~~~
    pip install requests
~~~  

Requests, por ejemplo, es un paquete muy utilizado para hacer solicitudes HTTP en Python.  

El paquete pip también te permite mantener tus librerías actualizadas o eliminar librerías que ya no usas.


