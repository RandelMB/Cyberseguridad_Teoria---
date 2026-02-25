
Voy a explicarlo mejor y sin adornos.

---


## 1. Entropía: la base de todo

Una **clave privada** debe ser impredecible. Si alguien puede adivinar cómo fue generada, esa clave vale poco.
La entropía es, básicamente, el nivel de aleatoriedad.  
Cuanta más entropía, más difícil es predecir la clave.
El problema aparece cuando se usan **contraseñas humanas** como base para generar claves. Las personas no eligen cadenas realmente aleatorias. Usan:
- Palabras comunes    
- Fechas    
- Nombres    
- Patrones simples    

Eso tiene **baja entropía**. Es corto, predecible y estructurado. Como resultado, aunque el sistema criptográfico sea fuerte, la entrada es débil.
Ahí entran el **salting** y la **expansión de claves**.

---
## 2. Salting (uso de sal)

Las contraseñas no deberían guardarse en texto plano. Se almacenan como un **hash criptográfico** (por ejemplo, usando SHA-256 o MD5).
Un hash es unidireccional: no se puede revertir directamente para obtener la contraseña original.
Pero eso no significa que esté protegido.

### El problema

Un atacante puede:
- Hacer **ataques de fuerza bruta** (probar todas las combinaciones posibles).    
- Hacer **ataques de diccionario** (probar listas de palabras comunes).    
- Usar tablas precalculadas (rainbow tables).

Si dos usuarios tienen la misma contraseña, tendrán el mismo hash. Eso facilita mucho el ataque.

---

### La solución: agregar sal

La sal es un valor aleatorio único que se añade a la contraseña antes de hacer el hash.
Fórmula simplificada:
```
hash = SHA(sal + contraseña)
```

Puntos clave:
- Cada usuario debe tener una sal distinta.    
- La sal no es secreta.    
- Se guarda junto al hash.    

¿Qué logra esto?
1. Si dos usuarios usan la misma contraseña, los hashes serán distintos.    
2. Las tablas precalculadas dejan de servir.    
3. El atacante debe recalcular cada intento específicamente para cada usuario.    

No hace imposible el ataque.  
Pero lo encarece en tiempo y recursos.

---

## 3. Expansión de claves (Key Stretching)

El salting protege contra ataques masivos precomputados.  
La expansión de claves protege contra la velocidad del ataque.
La idea es simple:  
Si generar un hash toma más tiempo, cada intento del atacante también tomará más tiempo.
En lugar de aplicar una sola vez el hash, se aplican miles o cientos de miles de iteraciones.
Ejemplo conceptual:

```
clave = hash(hash(hash(hash(...))))
```

Eso hace que:
- Para el sistema legítimo, el retraso es casi imperceptible.    
- Para un atacante que prueba millones de contraseñas, el costo se multiplica enormemente.    

Una de las funciones más usadas para esto es PBKDF2.
También se utiliza en estándares como WPA2 para proteger redes Wi-Fi.

---
## 4. Algo importante que suele confundirse

La expansión de claves **no hace que una contraseña débil se vuelva fuerte**.
Si la contraseña es "123456", seguirá siendo mala.
Lo que hace es:
- Ralentizar ataques.    
- Aumentar el costo computacional del adversario.    
- Comprar tiempo.    

La verdadera seguridad viene de:
- Alta entropía.    
- Sal única.    
- Función de derivación fuerte.    
- Buen manejo del almacenamiento.    
---
