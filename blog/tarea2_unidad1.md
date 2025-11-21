## Reto 1 - Simula el comportamiento de la tortuga usando solo print() e input()

### Enunciado  
Intenta recrear el movimiento de la tortuga únicamente con texto, usando funciones, print() e input() para pedir valores al usuario.

### Mi solución en Python
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

```
=== Reto 1: Simulador de tortuga 🐢 ===
¿Cuántos pasos debe avanzar la tortuga? 8
La tortuga avanzó 8 pasos.
Simulación del movimiento:
🐢--------
```

## Reto 2
###Crea el rastro de una tortuga moviéndose hacia abajo usando únicamente print() e input().
La salida esperada es similar a:

tortuga bajando

### Mi solución en Python
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
```
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

### Mi solución en Python
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
```
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


