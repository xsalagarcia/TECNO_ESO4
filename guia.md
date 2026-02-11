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

# Tipus de dades i operacions

Existeixen tipus de dades, que defineixen el tipus d'informació que representen, les operacions que hi podem
fer i l'efecte que té cada operació.

Crea la següent funció:

```python
def addition(a, b):
    print(f"Has passat un valor de tipus {type(a)} i un altre de tipus {type(b)}.")
    result = a + b
    print(f"La seva suma és {result}, i el tipus resultant és {type(result)}")
```

