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

Finalment, refactoritza el codi. Totes les funcions tenen una línia que és comuna, la primera.
Al principi del fitxer crea una funció anomenada `tell_me_the_types(a,b)` que contingui el següent codi:
```python
print(f"Has passat un valor de tipus {type(a)} i un altre de tipus {type(b)}.")
```
I substitueix la línia que s'està repetint a totes les funcions per una crida a aquesta funció.


