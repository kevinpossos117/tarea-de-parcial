# Taller de Modificadores de Acceso en Python

## Pregunta 1
**¿Cuáles de los siguientes atributos son accesibles desde fuera de la clase?**

- `x` 
- `_y`
- `__z` 


**Respuesta:** 

a,b

`x` y `_y` son accesibles directamente. `__z` solo mediante *name mangling*.  

---

## Pregunta 2
**Verdadero o Falso:** Los atributos privados en Python no pueden ser accedidos de ninguna manera desde fuera de la clase.  

**Respuesta:** ❌ **Falso.**  
Se pueden acceder usando *name mangling* (`obj._Clase__atributo`), aunque no es buena práctica.

---

## Pregunta 3
**¿Cuál es la forma correcta de acceder a un atributo privado en Python?**

a) Directamente con `obj.__atributo`  
b) Usando *name mangling* `obj._Clase__atributo`  
c) A través de un método *getter/setter* definido en la clase  

**Respuesta:** ✔️ La más correcta es **c)** (aunque b funciona, no es lo recomendado).  

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