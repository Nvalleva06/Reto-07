# Reto-07

### Ejercicios
1. Imprimir un listado con los números del 1 al 100 cada uno con su respectivo cuadrado.
2.  Imprimir un listado con los números impares desde 1 hasta 999 y seguidamente otro listado con los números pares desde 2 hasta 1000.
3.  Imprimir los números pares en forma descendente hasta 2 que son menores o iguales a un número natural n ≥ 2 dado
4. Imprimir los números de 1 hasta un número natural n dado, cada uno con su respectivo factorial
5. Calcular el valor de 2 elevado a la potencia n usando ciclos *for*.
6. Leer un número natural n, leer otro dato de tipo real x y calcular x^n usando ciclos for. **Disclaimer:** Trate de no utilizar el operador de potencia (**).
7. Diseñe un programa que muestre las tablas de multiplicar del 1 al 9.
8. Diseñar una función que permita calcular una aproximación de la función exponencial alrededor de 0 para cualquier valor x (real), utilizando los primeros n términos de la serie de Taylor. **Nota:** use *math* para traer la función exponencial y mostrar la diferencia entre el valor real y la aproximación.
$$e^x \approx exp(x,n) \approx \sum_{i=0}^{n}\frac{x^i}{i!}$$
9. Diseñar una función que permita calcular una aproximación de la función seno alrededor de 0 para cualquier valor x (real), utilizando los primeros n términos de la serie de Maclaurin. **Nota:** use *math* para traer la función seno y mostrar la diferencia entre el valor real y la aproximación.
$$sin(x) \approx sin(x,n) \approx \sum_{i=0}^{n} (-1)^i \frac{x^{2i+1}}{(2i+1)!}$$

## Solución

### Ejercicio 1
```python
#Imprimir un listado con los números del 1 al 100 cada uno con su respectivo cuadrado.
for n in range(1,101): #Creamos el buvle con el for in en el rango de 1 hasta 101 sin incluirlo 
 print(" El cuadrado de " + str(n) + " es " + str(n**2)) #imprimimos con su respectivo cuadrado
```

### Ejercicio 2
```python
#Imprimir un listado con los números impares desde 1 hasta 999 y seguidamente otro listado con los números pares desde 2 hasta 1000.

for n in range(1,1000,2): #Creamos el blucle en un rango de 1 hasta 1000 sin incluirlo con un salto de 2 para imprimir solo los impares
    print(n) #Se imprime la lista de impares
    
for n in range(2,1001,2): #Creamos el blucle en un rango de 2 hasta 1001 sin incluirlo con un salto de 2 para imprimir solo los impares
    print(n) #Se imprime la lista de pares
```

### Ejercicio 3
```python
# Imprimir los números pares en forma descendente hasta 2 que son menores o iguales a un número natural n ≥ 2 dado

n = int(input("Ingrese un número entero mayor o igual a 2: ")) #Pedimos que se ingrese el número

if n%2 != 0: #Comprobamos si n es par
        n -= 1 #Si no es par le restamos 1

for i in range(n, 1, -2): #Creamos el rango de n hasta 1 (sin incluir el 1 para que llegue hasta 2)
        print(i) #Imprimimos
```

### Ejercicio 4
```python
#Imprimir los números de 1 hasta un número natural n dado, cada uno con su respectivo factorial

n = int(input("Ingrese un número natural: ")) #Pedimos que se ingrese n

for i in range(1, n + 1): #Aca ponemos creamos el rango de 1 hasta n incluyendolo 

    facto = 1 #Creamos la variable facto y la definimos como 1 para iniciar el factorial en 1 para cada numero 1

    for j in range(1, i + 1): #Aca se crea el bucle que cálcula cada factoria desde 1 hasta n
        facto *= j #Se multiplica el factorial para ir acumulando las multiplicaciones 
        
    print(str(i) + "! = " + str(facto)) #Imprimimos
```

### Ejercicio 5
```python
#Calcular el valor de 2 elevado a la potencia n usando ciclos for.

n = int(input("Ingrese un número entero que no sea negativo: "))

resultado = 1 #Iniciaamos el resultado en 1

for i in range(n): #Multiplicamos 2 por sí mismo n veces
    resultado *= 2

print("2 elevado a la", n, "es:", resultado) #Imprimimos
```

### Ejercicio 6
```python
#Leer un número natural n, leer otro dato de tipo real x y calcular x^n usando ciclos for. Disclaimer: Trate de no utilizar el operador de potencia (**).

n = int(input("Ingrese un número natural mayor o igual a 0: ")) #Pedimos que ingrensen un numero natural

x = float(input("Ingrese un número real x: ")) #Pedimos que ingresen un número real

resultado = 1.0 #Inicializamos el resultado en 1

#Multiplicamos x por sí mismo n veces
for i in range(n):
    resultado *= x

print(x, "elevado a la", n, "es:", resultado) #Impirmimos
```

### Ejercicio 7
```python
#Diseñe un programa que muestre las tablas de multiplicar del 1 al 9.

for i in range(1, 10): #Recorremos los números del 1 al 9 para generar cada tabla
    print("Tabla del " + str(i) + ":") #Imprimimos el encabezado de la tabla
    
    for h in range(1, 11): #Recorremos del 1 al 10 para cada multiplicación de cada tabla
        resultado = i * h #Definimos resultado para las multiplicaiones
        print(str(i) + " x " + str(h) + " = " + str(resultado)) #Imprimimos
    
    print("------------") #Escribí esto para separar las tablas
```

### Ejercicio 8
```python
import math

def aproximar_exp(x:float, n:int) -> float: #Definimos una función que calcula una aproximación de e^x
    resultado = 0 #Iniciamos la suma acumulada en 0
    for i in range(n + 1): #Recorre desde 0 hasta n (inclusive)
        resultado += (x ** i) / math.factorial(i) #Sumamos cada término de la serie de Taylor
    return resultado #Retorna el resultado total

x = float(input("Ingrese el valor de x: ")) #Pedimos que ingrese un número real x
n = int(input("Ingrese el número de términos n: ")) #Pedimos que ingrese un número de términos n

aproximacion = aproximar_exp(x, n) #Calcula la aproximación de e^x usando la función
valor_real = math.exp(x) #Calcula el valor real de e^x con la función math.exp
diferencia = abs(valor_real - aproximacion)  #Calcula la diferencia entre el valor real y la aproximación

print("Aproximación:", str(aproximacion)) #Imprimios la aproximación
print("Valor real:", str(valor_real)) #Imprimios el valor real
print("Diferencia:", str(diferencia)) #Imprimios la diferencia
```

### Ejercicio 9
```python
import math 

def aproximar_seno(x:float, n:int) -> float: #Definimos una función que calcula sin(x) con n términos
    resultado = 0  #Iniciaamo el resultado en 0
    for i in range(n + 1):  #Itera desde 0 hasta n (inclusive)
        signo = (-1) ** i  #Alterna el signo: +, -, +, -, ...
        numerador = x ** (2 * i + 1)  #x elevado a (2i + 1)
        denominador = math.factorial(2 * i + 1)  #factorial de (2i + 1)
        resultado += signo * (numerador / denominador)  #Suma el término a la aproximación
    return resultado  #Devuelve la aproximación

x = float(input("Ingrese el valor de x (en radianes): "))  #Solicita x al usuario
n = int(input("Ingrese el número de términos n: "))  #Solicita cuántos términos usar

aproximacion = aproximar_seno(x, n)  #Calcula la aproximación
valor_real = math.sin(x)  #Calcula el valor real de sin(x)
diferencia = abs(valor_real - aproximacion)  #Calcula la diferencia absoluta

print("Aproximación:", str(aproximacion))  #Imprime la aproximación
print("Valor real:", str(valor_real))  #Imprime el valor real
print("Diferencia:", str(diferencia))  #Imprime la diferencia
```
