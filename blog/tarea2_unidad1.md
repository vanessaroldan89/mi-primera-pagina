## Reto 1 - Simula el comportamiento de la tortuga usando solo print() e input()

### Enunciado  
Intenta recrear el movimiento de la tortuga únicamente con texto, usando funciones, print() e input() para pedir valores al usuario.

### Mi solución
```python
def reto3():
print("=== Reto 1: Simulador de tortuga 🐢 ===")
pasos = input("¿Cuántos pasos debe avanzar la tortuga? ")
pasos = int(pasos)
print("La tortuga avanzó", pasos, "pasos.")
print("Simulación del movimiento:")
print("🐢" + "-" * pasos)
```

### Explicación  
En este primer ejercicio recreé el movimiento de la tortuga usando únicamente texto, sin gráficos. El programa le pide al usuario cuántos pasos quiere que avance la tortuga y convierte esa entrada a un número entero. Luego muestra una línea de flechas que representa el recorrido de la tortuga en la pantalla.

### Ejemplo de salida del programa

```python
=== Reto 1: Simulador de tortuga 🐢 ===
¿Cuántos pasos debe avanzar la tortuga? 8
La tortuga avanzó 8 pasos.
Simulación del movimiento:
🐢--------
```

## Reto 2
### Crea el rastro de una tortuga moviéndose hacia abajo usando únicamente print() e input().
La salida esperada es similar a:

tortuga bajando

### Mi solución
```python
def reto2():
    print("=== Reto 2: tortuga hacia abajo ===")
    pasos = int(input("¿Cuántos pasos quieres que baje la tortuga? "))
    print("\nPosición inicial:")
    print("🐢")
    print("\nMovimiento hacia abajo:")
    for i in range(pasos):
        print("│")
    print(f"\nLa tortuga bajó {pasos} pasos.")


# SOLO SE EJECUTA EL RETO 2
reto2()
```
### Explicación
En este ejercicio simulé que la tortuga baja en línea recta. Primero muestro la tortuga en la parte superior y luego imprimo una flecha hacia abajo por cada paso que el usuario indique. Todo se hace usando texto y ciclos, sin gráficos.

### Ejemplo de salida del programa
```python
=== Reto 2: tortuga hacia abajo ===
¿Cuántos pasos quieres que baje la tortuga? 45

Posición inicial:
🐢

Movimiento hacia abajo:
│
│
│
│
│
│
│
│
│
│
│
│
│
│
│
│
│
│
│
│
│
│
│
│
│
│
│
│
│
│
│
│
│
│
│
│
│
│
│
│
│
│
│
│
│
La tortuga bajó 45 pasos.
```

## Reto 3
###Enunciado
Ahora la tortuga no solo avanza: también gira.

### Mi solución
```python
def reto3():
    print("=== Reto 3: girar y dibujar una L ===")

    pasos_derecha = int(input("¿Cuántos pasos avanza la tortuga a la derecha? "))
    pasos_abajo = int(input("¿Cuántos pasos baja la tortuga después de girar? "))

    # Primera parte: movimiento a la derecha
    print("\nMovimiento hacia la derecha:")
    linea = "🐢" + "-" * pasos_derecha
    print(linea)

    # Segunda parte: movimiento hacia abajo
    print("\nMovimiento hacia abajo:")
    # imprimir espacio en blanco para alinear la columna
    espacio = " " * (1 + pasos_derecha)
    for i in range(pasos_abajo):
        print(espacio + "|")

    print("\nLa tortuga dibujó una L con los pasos indicados.")
    

# Ejecutar solo el reto 3
reto3()
```
### Explicación  
En este ejercicio la idea es que la tortuga haga una “L” usando solo texto. Primero uso input() para preguntarle al usuario cuántos pasos debe avanzar hacia la derecha y cuántos debe bajar. Luego, con print(), voy mostrando las flechas que forman la figura: una línea horizontal y después las flechas hacia abajo. Básicamente es imaginar el camino de la tortuga, pero usando solo lo que escribimos en pantalla.

### Ejemplo de salida del programa
```python
=== Reto 3: girar y dibujar una L ===
¿Cuántos pasos avanza la tortuga a la derecha? 6
¿Cuántos pasos baja la tortuga después de girar? 9

Movimiento hacia la derecha:
🐢------

Movimiento hacia abajo:
       |
       |
       |
       |
       |
       |
       |
       |
       |

La tortuga dibujó una L con los pasos indicados.
```
## Reto 4
### Enunciado
Reescribe los retos anteriores creando funciones que representen los movimientos de la tortuga solo con texto.
### Mi solución en Python
```python
def adelante(n):
    """
    Dibuja el movimiento hacia la derecha (→) por n pasos.
    """
    if n > 0:
        print("→" * n)

def abajo(n):
    """
    Dibuja el movimiento hacia abajo (↓) por n pasos, 
    alineando cada flecha verticalmente.
    """
    if n > 0:
        for _ in range(n):
            print("↓")

print("\n--- Patrón en L ---")
adelante(8)
abajo(5)
```
### Explicación
Aquí ya no uso `input()`, sino que creo funciones que hacen el trabajo por mí. `adelante(n)` imprime la tortuga moviéndose hacia la derecha y va guardando la posición para que después `abajo(n)` pueda bajar justo debajo. Al final, con estas funciones dibujo una pequeña “L” usando solo texto.

### Ejemplo de salida del programa
```python
--- Patrón en L ---
→→→→→→→→
↓
↓
↓
↓
↓
```

## Reto 5
### Enunciado
Ajusta tus funciones para que la tortuga pueda bajar escalones.
Cada escalón debe conservar la posición horizontal acumulada y dibujar correctamente tanto el tramo horizontal como el vertical.
### Mi solución
```python
# =========================================================
# 1. ESTADO GLOBAL (Necesario para recordar la posición)
# =========================================================
posicion_x = 0  # Posición horizontal (indentación)

# =========================================================
# 2. FUNCIONES DE MOVIMIENTO CON ESTADO
# =========================================================

def adelante(n):
    """
    Dibuja el movimiento hacia la derecha (+) y actualiza la posición horizontal.
    """
    global posicion_x
    if n > 0:
        # 1. Imprime los espacios de indentación acumulados hasta ahora
        indentacion = " " * posicion_x
        
        # 2. Dibuja el tramo horizontal (usamos '+' como en tu ejemplo)
        print(indentacion + "+" * n)
        
        # 3. Actualiza la posición X para el siguiente movimiento
        posicion_x += n

def abajo(n):
    """
    Dibuja el movimiento hacia abajo (↓) alineado con la posición horizontal actual.
    """
    global posicion_x
    if n > 0:
        # La indentación se basa en la posición horizontal acumulada
        espacio = " " * posicion_x
        
        # Dibuja cada tramo vertical
        for _ in range(n):
            print(espacio + "↓")
        
        # NOTA: El movimiento vertical NO cambia la posicion_x

# =========================================================
# 3. FUNCIÓN DE COMPOSICIÓN (Dibuja la escalera)
# =========================================================

def escalera(num_escalones, pasos_h, pasos_v):
    """
    Dibuja una serie de escalones, reiniciando la posición_x para empezar.
    """
    global posicion_x
    # Reinicia el estado para que la escalera empiece siempre desde el borde
    posicion_x = 0 
    
    print(f"\n--- Dibujando Escalera de {num_escalones} escalones ---")
    
    for i in range(num_escalones):
        print(f"\n# Escalón {i + 1}")
        adelante(pasos_h)
        abajo(pasos_v)

# =========================================================
# 4. EJECUCIÓN DEL RETO 5
# =========================================================

# Dibuja la escalera del ejemplo: 3 escalones de 5 pasos horizontales y 2 verticales.
escalera(num_escalones=3, pasos_h=5, pasos_v=2)
```

### Explicación
En este último reto hice que la tortuga bajara una escalera usando solo texto. Para lograrlo reutilicé las funciones adelante() y abajo() del reto anterior, pero esta vez las puse a trabajar varias veces seguidas para formar cada escalón. La tortuga primero avanza un poco hacia la derecha y luego baja, y ese patrón se repite según la cantidad de escalones que uno elija. Gracias a que voy guardando la posición horizontal, cada parte queda alineada y la escalera se va dibujando de manera ordenada. Al final es como ver a la tortuga bajar escalón por escalón, pero todo hecho con texto.

### Ejemplo de salida del programa

```python
--- Dibujando Escalera de 3 escalones ---

# Escalón 1
+++++
     ↓
     ↓

# Escalón 2
     +++++
          ↓
          ↓

# Escalón 3
          +++++
               ↓
               ↓
```
