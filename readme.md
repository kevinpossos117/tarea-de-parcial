# Taller de Modificadores de Acceso en Python

## Pregunta 1
**¿Cuáles de los siguientes atributos son accesibles desde fuera de la clase?**

- `x` 
- `_y`
- `__z` 


**Respuesta:** 

a,b

`x` y `_y` son accesibles directamente. `__z` solo mediante "name mangling".  

---
## pregunta 2

class A:
    def __init__(self):
        self.__secret = 42

a = A()
print(hasattr(a, '__secret'), hasattr(a, '_A__secret'))


**¿que imprime?**

**respuesta**


false true


![alt text](image.png)





---
## Pregunta 3
**Verdadero/Falso (explica por qué)**

- El prefijo _ impide el acceso desde fuera.  Falso. Solo es convención.
- El prefijo __ hace imposible acceder.  Falso. Se puede acceder con name mangling.
- El name mangling depende del nombre de la clase.  Verdadero.
---
## pregunta 4

class Base:
    def __init__(self):
        self._token = "abc"

class Sub(Base):
    def reveal(self):
        return self._token

print(Sub().reveal())

**que imprime y por que no da error?**

**respuesta**

Imprime: abc.

No hay error porque _token es solo convención, no restricción real.

![alt text](image-1.png)

---

## Pregunta 5

class Base:
    def __init__(self):
        self.__v = 1

class Sub(Base):
    def __init__(self):
        super().__init__()
        self.__v = 2
    def show(self):
        return (self.__v, self._Base__v)

print(Sub().show())

**cual es la salida?**

**resouesta**


Salida: (2, 1).


![alt text](image-2.png)

---

## pregunta 6

**Identifica el error**

class Caja:
__slots__ = ('x',)
c = Caja()
c.x = 10
c.y = 20

**por que**

Con __slots__, solo se pueden definir atributos listados en la tupla. Aquí solo x está permitido. Cuando intentamos asignar c.y, Python lanza un error porque y no está en __slots__.

**error**

![alt text](image-3.png)

---

## Ejercicio 7

**Rellenar espacios**


class B:
    def __init__(self):
        self._____ = 99

**respuesta**
self._valor = 99

---

## ejercicio 8

**Lectura de métodos “privados”**

class M:
    def __init__(self):
        self._state = 0
    def _step(self):
        self._state += 1
        return self._state
    def __tick(self):
        return self._step()

m = M()
print(hasattr(m, '_step'), hasattr(m, '__tick'), hasattr(m, '_M__tick'))

**¿Qué imprime y por qué?**

True False True

**¿por que?**

_step existe asi que da = True.

__tick no existe con ese nombre (se manglea) y por eso da = False.

_M__tick existe tras el name mangling asi que da = True.

---
