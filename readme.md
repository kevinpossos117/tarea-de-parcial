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

a. El prefijo _ impide el acceso desde fuera.  Falso. Solo es convención.
b. El prefijo __ hace imposible acceder.  Falso. Se puede acceder con name mangling.
c. El name mangling depende del nombre de la clase.  Verdadero.

---

## Pregunta 4
**¿Por qué se usan los guiones bajos (`_` y `__`) en los atributos de clase?**

- Para indicar el **nivel de acceso**: público, protegido o privado.  
- Aunque en Python no hay verdadera privacidad, la convención ayuda a escribir código más organizado y seguro.

---

## Pregunta 5
**Explique brevemente la diferencia entre un atributo protegido y uno privado.**

- **Protegido (`_atributo`)**: accesible dentro de la clase y subclases, pero no debería usarse desde fuera (solo convención).  
- **Privado (`__atributo`)**: Python aplica *name mangling*, lo que lo hace más difícil de acceder desde fuera.  