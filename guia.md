<!-- TOC -->
* [Preparar l'entorn](#preparar-lentorn)
* [Primer programa](#primer-programa)
* [Tipus de dades i operacions](#tipus-de-dades-i-operacions)
  * [resum](#resum)
  * [Curiositat](#curiositat)
* [Condicionals](#condicionals)
  * [`if`, `else`, `elif`](#if-else-elif)
* [Bucles](#bucles)
  * [`while "condició"`](#while-condició)
  * [Un parell de jocs senzills](#un-parell-de-jocs-senzills)
    * [Un joc classic: Endevinar un número.](#un-joc-classic-endevinar-un-número)
    * [Pedra, tisores, paper](#pedra-tisores-paper)
  * [`for "element" in "col·lecció d'elements":`](#for-element-in-collecció-delements)
* [Col·leccions, seqüències i estructures de dades bàsiques a Python](#colleccions-seqüències-i-estructures-de-dades-bàsiques-a-python)
  * [Range()](#range)
  * [Tuples (`tuple`)](#tuples-tuple)
  * [Llistes (`list`)](#llistes-list)
  * [Diccionaris (`dict`)](#diccionaris-dict)
<!-- TOC -->

# Preparar l'entorn

1. Anar a la pàgina de descàrregues de l'IDE 
Pycharm: https://www.jetbrains.com/es-es/pycharm/download/ i descarregar la versió corresponent segons
el sistema operatiu que tingueu.
2. Anar a la pàgina de la *Python Software Foundation*: https://www.python.org i aneu a la secció de 
descàrregues (downloads). Seleccioneu la descàrrega d'acord amb el vostre sistema operatiu i seguiu les
instruccions. **Per a Windows o Mac seleccioneu descarregar l'instal·lador i executeu-lo**.

# Primer programa

Aneu al menú tipus hamburguesa que es situa a dalt a l'esquerra i seleccioneu "New project...". Fixeu-vos 
a on esteu creant el projecte (i si cal, modifiqueu-lo), seleccioneu el tipus d'intèrpret `venv` i cliqueu
a `create`.

Desplegueu l'estructura del projecte a la icona de carpeta i, amb el botó dret feu click a la carpeta
principal del projecte -> new -> python file. Li donem el nom primer_programa al fitxer.

Escriviu el següent codi:

```python
def say_hello(name):
    print(f"Hello {name}!")

say_hello("Berenguer")
```

<details>
    <summary><b>Explicació sobre com s'escriu un bloc de codi en Python (Sintaxi) i com es declara una funció</b></summary>

        Si observes, la funció sempre va precedida per la paraula clau `def`, seguit del nom de la funció i un
        parèntesi. Dins el parèntesi pot haver-hi paràmetres o no. En aquest primer exemple n'hi ha un, que passa informació
        a la funció (`name`).

        Per a qualsevol bloc (codi dins una funció, un condicional, un bucle) la línia que defineix el bucle
        acaba amb `:`. I el codi que està contingut dins el bloc està *indentat*. Això vol dir que té un o varis
        espais (normalment 4) o tabulats, sempre els mateixos dins el mateix bloc. Així, l'intèrpret sap quines
        són les instruccions dins el bloc.

        Una funció també es pot utilitzar la paraula clau `return` per sortir de la funció. En aquest primer 
        exemple no hi és (no és necessari), però és imprescindible perquè la funció retorni un valor o per 
        tornar en un moment donat encara que quedin instruccions dins el bloc.

</details>

# Tipus de dades i operacions

Existeixen tipus de dades, que defineixen el tipus d'informació que representen, les operacions que hi podem
fer i l'efecte que té cada operació.

Crea les següents funcions:

```python
def addition(a, b):
    print(f"Has passat un valor de tipus {type(a)} i un altre de tipus {type(b)}.")
    result = a + b
    print(f"La seva suma és {result}, i el tipus resultant és {type(result)}")

def substraction(a, b):
    print(f"Has passat un valor de tipus {type(a)} i un altre de tipus {type(b)}.")
    result = a * b
    print(f"La seva resta és {result}, i el tipus resultant és {type(result)}")

def product(a, b):
    print(f"Has passat un valor de tipus {type(a)} i un altre de tipus {type(b)}.")
    result = a * b
    print(f"La seva multiplicació és {result}, i el tipus resultant és {type(result)}")

def division(a, b):
    print(f"Has passat un valor de tipus {type(a)} i un altre de tipus {type(b)}.")
    result = a / b
    print(f"La seva divisió és {result}, i el tipus resultant és {type(result)}")

def integer_division(a, b):
    print(f"Has passat un valor de tipus {type(a)} i un altre de tipus {type(b)}.")
    result = a // b
    print(f"La seva divisió entera és {result}, i el tipus resultant és {type(result)}")
```

Crida les diferents funcions passant els valors d'aquesta manera:

```python
addition(5, 6)
addition(5.0, 6.0)
addition("5", "6")
addition("5", 6)  # Donarà error. Intenta saber perquè
```

Fes-ho per la resta de funcions. Si una línia de codi et dóna error, l'hauràs d'eliminar o modificar perquè
la resta del codi pugui ser executat (de moment, posa el signe `#` a l'inici i així no s'executarà.
Posa a prova totes les funcions.

Finalment, **refactoritza el codi**. Totes les funcions tenen una línia que és comuna, la primera.
Al principi del fitxer crea una funció anomenada `tell_me_the_types(a,b)` que contingui el següent codi:
```python
print(f"Has passat un valor de tipus {type(a)} i un altre de tipus {type(b)}.")
```
I substitueix la línia que s'està repetint a totes les funcions per una crida a aquesta funció.

## resum
> Amb aquest exercici has vist que, segons com escriguis un nombre, aquest quedarà representat
> amb un tipus de dada diferent: `int`, `float`, `str`. I cada tipus de dades permet diferents operacions
> i l'efecte d'aquestes també depèn del tipus de dades. Entre altres operacions, has vist la suma (`+`,
> la resta (`-`), la multiplicació (`*`) i dos tipus de divisions (`/`, `//`). Aquests, es diuen operadors
> aritmètics.

## Curiositat

Els diners, en la majoria llenguatges de programació, no se solen representar amb el tipus `float`, que és
el que intuïtivament faries servir quan has de considerar els cèntims d'euro.
Crea un fitxer anomenat **`demo_suma_float.py`**, posa el següent codi i mira si fa bé la suma...:
```python
suma = 0.1 + 0.1 + 0.1
print(suma)
```

# Condicionals

## `if`, `else`, `elif`

Amb scratch hem vist que podem executar un tros de codi o un altre segons si es compleix una condició. Tot 
llenguatge de programació permet això.

Crea un nou fitxer anomenat **`condicionals_1.py`**, dins, escriu una funció que tingui per nom 
`numeric_to_name_grade` (o en català `de_nota_numèrica_a_nom`), que accepti un valor anomenat `grade`.

<details>
    <summary><b>Ajuda</b></summary>
        Recorda que per crear una funció s'utilitza la paraula clau <code>def</code>. Queda algo així:
        <pre><code>
        def nom_funcio(parametre1, parametre2):
            # codi
        </code></pre>
</details>

Dins la funció poses el següent:

```python
if grade < 5:
    # Aquest bloc de codi només s'executa en cas que la nota sigui inferior a 5
    print("Suspès")
elif grade <= 6:
    # Aqueset bloc de codi només s'executa en cas que l'anterior bloc no s'executi i la nota sigui igual o inferior a 6-
    print("Aprovat")
elif grade <= 8:
    # Aqueset bloc de codi només s'executa en cas que si l'anterior bloc no s'executi i la nota sigui igual o inferior a 8 
    print("Notable")
else:
    # Aqueset bloc de codi només s'executa en cas que els altres blocs no s'hagi executat.
    print("Excel·lent")
```
> Pots veure també que les línies que comencen amb `#` son comentaris. Aquestes línies no s'executen. L'intèrpret
> de Python les ignora. Les pots fer servir sempre que vulguis per recordar què fa el codi que has escrit.

Ara crida la funció, p.ex.:
```python
numeric_to_name_grade(4)
```
Fes diverses crides, amb diferents notes i comprova que té el funcionament esperat.

Crea un nou fitxer anomenat **`condicionals_2.py`**, crea una funció que tingui per nom `age_classifier`
i que accepti un únic parameter anomenat `age`. Si l'edat és menor de 12, imprimeix "Infant", si és més de 12
i menys de 18, "Adolescent", si està entre 18 i menys de 90, "Adult" i si és 90 o més "Temps de descompte... tic, tac.".
Intenta reproduir un esquema similar al que hem vist a l'exemple de les notes.

# Bucles

## `while "condició"`

Aquesta ordre s'utilitza per generar un bucle que es va repetint mentre es compleixi una condició.

Crea un fitxer que es digui **`exemple_while_1.py`**, posa el següent codi, intenta entendre'l abans d'executar-lo.
A continuació executa'l:

```python
password = "abracadabra"
answer = ""
while answer != password:
    
    # La funció input atura el programa per demanar que escriguis a la consola de text.
    # S'espera que l'usuari escrigui alguna cosa i quan es pressiona Enter retorna el text que l'usuari
    # ha escrit (en aquest cas, el text quedarà desat a la variable answer).
    answer = input("Escriu la clau de pas: ")

print("Molt bé, has endevinat la clau de pas")
```

## Un parell de jocs senzills

### Un joc classic: Endevinar un número.

> Per això farem servir una funció que no es troba integrada al llenguatge, però sí que està incorporada a una biblioteca
> (mal traduïdes, llibreries (de library))
> que habitualment està disponible a través de biblioteques integrades de Python. Les biblioteques,
> en programació, agrupen funcions que estan relacionades entre elles d'alguna manera (p.ex. matemàtiques, generació de nombres
> aleatoris...). Com que necessitarem generar un nombre aleatori, importarem funcions de la biblioteca `random`.
> 
> Pensa que si totes les funcions, de totes les biblioteques estiguessin disponibles sempre, tindries un munt
> de noms, el que et generaria confusió i podries cometre errors, a més que alguns noms coincidirien.

Crea un nou fixer **`guess_the_number.py`**

Al principi del fitxer python, s'importa la biblioteca o les funcions de la biblioteca. Pots copiar aquest codi i acabar-lo:

```python
from random import randint  # Ara ja podem utilitzar la funció randint

number = randint(1, 10)  # Aquí generem un nombre entre l'1 i el 10 i el guardem a la variable number.

answer = 0  # Creem una variable anomenada answer i li donem un valor qualsevol que sabem, no pot ser el mateix que la variable number. 

while answer != number:
    answer = int(input("Endevina el número (del 1 al 10): "))  # Amb int(), la resposta obtinguda a answer es convertirà en un tipus enter.
    
    """
    Acaba tú el codi d'aquest bucle. Si el nombre que introdueix el jugador és més alt, imprimir (print) que el 
    nombre a endevinar és més baix. Si el nombre és més baix, imprimir que és més alt. I en cas contrari
    donar la enhorabona al jugador, ja que l'haurà endevinat.
    """
```

> També pots fer comentaris de diverses línies de codi amb """ comentari... """

### Pedra, tisores, paper

Anem a fer quelcom molt similar per poder jugar a *Pedra, tisores, paper*. Crea un nou fitxer, que el pots
anomenar **`paper_stone_scissors.py`**, còpia el següent codi i acaba'l.

```python
from random import randint  # Ara ja podem utilitzar la funció randint

options = ["pedra", "tisores", "paper"]
"""options és una llista amb 3 paraules. La posició 0 és pedra, tisores és la posició 1 i paper és la posició 2"""

repeat = "s"

while repeat == "s":
    """
    Bucle, mentre repetir sigui s
    """

    machine_option = options[randint(0, 2)]  # A partir d'un nombre aleatori, agafarem la paraula 0, 1 o 2 de la llista i la desarem a la variable machine_option

    answer =  # <--utilitza input per demanar a l'usuari que escrigui pedra, tisores o paper i deses el valor a answer.
    
    if answer == machine_option:
        # Un empat
        print("Empat")
        
    elif answer == options[0]:  
        # L'usuari ha respost pedra
        
        if machine_option == options[1]:
            # I la màquina tisores
            print(f"Has guanyat!, jo tenia {machine_option}")
            
        else:
            # La màquina paper
            print(f"He ganao, bacalao. Tenia {machine_option}")
        
    elif answer == options[1]:  
        # L'usuari ha respost tisores
        

    """
    Acaba tú el codi.

    utilitza input per demanar a l'usuari que escrigui pedra, tisores o paper.

    Utilitzant els condicionals que coneixes comparant el que ha escrit l'usuari amb el valor de 
    machine_option, decideix qui guanya i informa a l'usuari amb print().

    Opcional: Pots fer un codi més robust comprovant que l'usuari escriu exactament pedra, tisores o paper,
    i en cas que no, tornar a demanar una opció dins les disponibles. La comprovació es pot fer fàcilment
    amb `if answer in options...`

    Demana a l'usuari si vol tornar a jugar amb input(). 
    Per tornar a jugar, escriure la lletra s i apretar enter 
    (fixa't en la condició per seguir dins el bucle que estem).
    """
```

## `for "element" in "col·lecció d'elements":`

Sense entrar en molts detalls, la instrucció `for` ens permet recórrer una col·lecció d'elements. El més
important per utilitzar `for` és entendre què són les col·leccions, de manera que simplement crea un fitxer anomenat
**`demo_for.py`**, posa el següent codi, i executa'l per veure'n el resultat (modifica el comentari pertinent).

```python
for i in range(11):
    #  Escriu aquí, en forma de comentari, què fa aquest bucle.
    print(i)
```

Llavors segueix amb el [següent apartat](#colleccions-seqüències-i-estructures-de-dades-bàsiques-a-python)


# Col·leccions, seqüències i estructures de dades bàsiques a Python

Ens referirem a col·leccions com a contenidors que tenen diversos elements dins seu. Fins ara havíem dit
que una variable pot desar un valor. Però a vegades ens interessa guardar un conjunt de valors relacionats entre
ells, com una llista de noms.

Ens referirem a seqüències com una col·lecció els elements de la qual estan ordenats.

Les estructures de dades més bàsiques que podem considerar col·leccions són els tipus `list`, `tuple` i `dict`.
Addicionalment, sovint es fa servir la funció `range()` per crear una seqüència de nombres. A més, el tipus `str`
(Una cadena de text), també es pot tractar com una seqüència.

> Per accedir directament a l'element d'una seqüència s'utilitza el nom de la seqüència i els claudàtors `[]`.
> Es pot definir un sol element, començant a comptar pel 0. Si utilitzem nombres negatius es compta des del 
> final, i es pot agafar un interval utilitzant `[a:b]`, on `a` seria el primer element i l'últim el que ve
> abans de `b`

> Es pot comprovar si un element està dins una col·lecció amb l'operador `in`:
> ```python
> if element in collection:
>     print(f"{element} is in the collection" )
> ```

## Range()

Range és una funció que retorna una seqüència de nombres. Els paràmetres que pot acceptar són 
```range(start, stop, step=1)```, i almenys s'ha d'especificar el paràmetre `stop`.

Has vist, amb l'exemple de [`for`](#for-element-in-collecció-delements) com hem creat una seqüència de nombres.

Crea un fitxer anomenat **`taules_de_multiplicar.py`**

Acaba el següent codi:

```python
number = int(input("De quin número vols la taula de multiplicar? "))

print(f"La taula del {number}:")

# Crea el bucle for amb una seqüència de nombres, del 0 al 10 (els dos inclosos).
    # Per cada iteració imprimeix n x number = n * number

""" 
Opcional:
Si t'ha semblat senzill pots complicar-ho incorporant el codi anterior dins un bucle while de manera
pregunti a l'usuari si vol veure una altre taula de multiplicar. En cas de que escrigui "s", tornar a preguntar
De quin nombre vols la taula de multiplicar?
"""
```

## Tuples (`tuple`)

Les tuples són elements ordenats en una estructura de dades que no es pot modificar una vegada creada.

Per crear una tupla es posen els valors que vols incorporar tots dins un parèntesi.

Crea un fitxer anomenat **`exemple_tupla.py`**, posa-hi el següent codi, executa'l i mira d'entendre'l.

```python
solar_system_planets = ("Mercuri", "Venus", "Terra", "Mart", "Júpiter", "Saturn", "Urà", "Neptú")

any_planet = input("Escriu el nom d'un planeta: ")
if any_planet in solar_system_planets:
    print(f"El planeta {any_planet} pertany al sistema solar")
else:
    print(f"No tinc ni punyetera idea d'on està el planeta {any_planet}")

print(f"Informació: El planeta més pròxim al sistema solar és {solar_system_planets[0]}")
print(f"Informació: El planeta més llunyà al sistema solar és {solar_system_planets[-1]}")
print(f"Informació: Els 3 primers planetes del sistema solar son {solar_system_planets[0:3]}")

```

Crea un fitxer anomenat **`dni_calculator.py`**, posa-hi el següent codi i completa'l:

```python

# Crea una tupla on tinguis la següent seqüència de lletres: 
# "T", "R", "W", "A", "G", "M", "Y", "F", "P", "D", "X", "B", "N", "J", "Z", "S", "Q", "V", "H", "L", "C", "K", "E"

def give_me_the_letter(dni):
    """
    Donat un dni, retorna la lletra corresponent.
    """
    # Per calcular la lletra s'utilitza el residu de la divisió entera del nombre del dni entre 23. Per això utilitzem
    # l'operador "%": Això ho tens a continuació.
    r = dni % 23  # r és la variable que desa el residu
    
    # El residu (a la variable r) determina, d'acord amb les lletres que prèviament hem ordenat, la lletra que li 
    # correspon al número. Utilitza tupla_lletres[r] per recuperar i retornar-la
    return #...
    

# Demana a l'usuari que introdueixi un nombre de dni i el guardes a una variable anomenada dni. Converteix la
# resposta de l'usuari a tipus enter (dni = int(input(...   )

# crida la funció give_me_the_letter i fes un print per indicar la lletra que li correspon al dni que l'usuari ha escrit.

```

## Llistes (`list`)

Les llistes són com les tuples, però podem afegir o treure elements una vegada han estat creades.
La llista és un objecte que té mètodes com `append()`, `clear()`, `sort()`, `pop()` entre molts altres,
que permeten afegir, buidar completament, ordenar, o extreure un element de la llista respectivament.

Es poden crear com les tuples, però en comptes del parèntesi (`()`), s'utilitzen els claudàtors (`[]`).

Crea un fitxer anomenat **`lists_example.py`** i posa el següent codi, executa'l i mira d'entendre'l:

```python
guests = []  # Crea una llista, buida en aquest cas.

while True:
    """
    Amb While True el bucle no s'acaba mai perquè True és el valor que s'avalua (veritat).
    Més a baix, farem servir la paraula break per poder sortir del bucle
    """

    answer = input("Escriu el nom d'un convidat, o la paraula 'prou' si ja has acabat: ")
    if answer.upper() != "PROU":  # amb el mètode upper() convertim el text a majúscules abans d'avaluar-lo. Així l'usuari pot escriure Prou, PROU, prou....
        guests.append(answer)
    else:  # L'usuari ha escrit "prou" i s'executa break per sortir del bloc.
        break

print(f"Els convidats a la festa són {guests}")
```

## Diccionaris (`dict`)

Els diccionaris són col·leccions que, a priori, no tenen un ordre concret. Cada ítem de la col·lecció té
una clau i un valor. Els ítems es recuperen indicant la clau. Com quan utilitzes un diccionari, on, a partir d'una
paraula (clau), recuperes la definició d'aquesta (valor). **Cada clau ha de ser única**.

Per crear un diccionari s'utilitzen `{}`.

Creació d'un diccionari buit:
```python
my_empty_dict = {}
```

Creació d'un diccionari amb alguns valors:
```python
my_little_dict = {"Taronges": 8, "Mangos": 9, "Cireres": 9}  # El nom de la fruita seria la clau, el valor un número en aquest cas.
my_other_dict = {"Lluís": "Notable", "Conxita": 8, }  # El nom de la persona és la clau, el valor és la nota. Poden ser de diferents tipus.
```

També podem **afegir o actualitzar** un ítem a un diccionari existent:
```python
my_empty_dict = {}
my_empty_dict["Lluís"] = "Notable"  # Afegim un ítem. Clau = "Lluís", valor = "Notable". Si ja existís Lluís, s'actualitza la nota.
my_empty_dict["Conxita"] = 8
```

**Recuperem** els valors a través de la clau entre claudàtors: 
```python
my_other_dict = {"Lluís": "Notable", "Conxita": 8, }
nota_lluis = my_other_dict["Lluís"]
print(f"La nota d'en Lluís és {nota_lluis}")
```

Quan intentem **recuperar un ítem que no existeix, tindrem un error `KeyError`**. Una manera d'evitar l'error
seria:

```python
my_other_dict = {"Lluís": "Notable", "Conxita": 8, }
alumne = input("Nom de l'alumne: ")
if alumne not in my_other_dict:  # element in some_dictionary es compleix si element és la clau d'algun ítem. Neguem la condició amb `not`
    print("Aquest alumne no existeix")
else:
    print(f"La nota de l'alumne/a {alumne} és {my_other_dict[alumne]}")
```

**Per iterar les claus** d'un diccionari
```python
my_other_dict = {"Lluís": "Notable", "Conxita": 8, }
for name in my_other_dict:  # name és la variable que, a cada iteració tindrà el valor de la clau que estem iterant.
    print(name)
```

**Per iterar els elements** d'un diccionari
```python
my_other_dict = {"Lluís": "Notable", "Conxita": 8, }
for name, grade in my_other_dict.items():  # name, la clau de cada iteració. grade, el valor corresponent.
    print(f"L'alumne/a {name} ha tret {grade}")
```

Crea un fitxer anomenat **`comptador_de_lletres.py`**, posa i completa el següent codi segons les instruccions:

```python
def word_counter(text):
    # Crea un diccionari buit que es digui "result". (result = {})
    for letter in text: # Recorda que podem tractar els tipus str com si fossin una seqüència.
        """
        Dins aquest bucle, cada iteració és una lletra del text.
        """
        
        # Amb un if, comprova si el diccionari conté la clau corresponent a la lletra de la iteració (in, sense not).
            # Si hi és, s'executa això dins el bloc if
            result[letter] = result[letter] + 1
        # Dins el bloc else (la lletra encara no cap clau al diccionari)
            # Crea una nova entrada on la clau sigui la lletra corresponent i el seu valor sigui 1
    
    # Retorna el diccionari amb la instrucció result (per acabar la funció, fora del bucle for)
    # return...

# Crida la funció word_counter passant el text 
# "Un perso en la prisión de Prúsia apresó a un preso con una persiana persa", 
# desant el diccionari obtingut a una variable.

# itera tots els ítems amb un bucle for (for clau, valor in my_dictionary.items()) i 
# a cada iteració fes un print que indiqui la lletra, i el nombre associat. Algo així com
"""
Lletra U: 1 vegades
Lletra n: 7 vegades
Lletra  : 14 vegades
Lletra p: 6 vegades
Lletra e: 7 vegades
Lletra r: 7 vegades
Lletra s: 7 vegades
Lletra o: 3 vegades
Lletra l: 1 vegades
Lletra a: 8 vegades
Lletra i: 4 vegades
Lletra ó: 2 vegades
Lletra d: 1 vegades
Lletra P: 1 vegades
Lletra ú: 1 vegades
Lletra u: 2 vegades
Lletra c: 1 vegades
"""

```




