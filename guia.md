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

Aquesta ordre s'utilitza per generar un bucle que va iterant sobre cada element d'una llista o conjunt
d'elements (un iterable).









