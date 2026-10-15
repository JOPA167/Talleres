# Taller Individual Nro. 1 - José Ramírez Jiménez

## Primeros pasos en programación funcional

**Semana:** 1

### Objetivos

* Conocer las herramientas que utilizará en la asignatura: GitHub Codespaces, SDKMAN, Scala-CLI.
* Familiarizarse con cada una de las herramientas, especialmente el entorno Codespaces.
* Crear su primer programa funcional.

---

## Actividad N1

Se ejecutaron los siguientes comandos en la terminal de GitHub Codespaces para instalar los complementos requeridos: Java, sbt y Scala CLI, mediante SDKMAN.

### Instalación de Java

```bash
sdk list java
sdk install java 25.0.1.0+8-open
```

**Evidencia**

![Evidencia - Terminal - Instalación de Java](img/01-sdkman-java.jpeg)

### Instalación de sbt

```bash
sdk list sbt
sdk install sbt 2.0.10
```

**Evidencia**

![Evidencia - Terminal - Instalación de sbt](img/02-sdkman-sbt.jpeg)

### Instalación de Scala CLI

```bash
sdk list scalacli
sdk install scalacli 1.18.0
```

**Evidencia**

![Evidencia - Terminal - Instalación de Scala CLI](img/03-sdkman-scalacli.jpeg)

---

## Actividad N2

Se ejecutaron las herramientas REPL de los lenguajes de programación Java, Scala y Python, en tres ventanas de terminal distintas:

1. Primera ventana: `jshell`
2. Segunda ventana: `scala`
3. Tercera ventana: `ipython`

### Java (jshell)

```bash
jshell
```

```java
var nums = List.of(1, 2, 3, 4, 5);
nums.stream().map(n -> n * 10).toList()
record Tuple(int x, int y){}
nums.stream().map(n -> new Tuple(n, n * n)).toList()
nums.stream().filter(n -> n % 2 == 0).toList()
nums.stream().reduce(1, (n1, n2) -> n1 * n2)
```

**Evidencia - Terminal - Java**

![Evidencia - Terminal - Java](img/05-terminal-java-jshell.jpeg)

### Scala (scala)

```bash
scala
```

```scala
val nums = List(1, 2, 3, 4, 5)
nums.map(_ * 10)
nums.map(n => (n, n * n))
nums.filter(n => n % 2 == 0)
nums.reduce((n1, n2) => n1 * n2)
```

**Evidencia - Terminal - Scala**

![Evidencia - Terminal - Scala](img/06-terminal-scala.jpeg)

### Python (ipython)

```bash
ipython
```

```python
lst = [1, 2, 3, 4, 5]
list(map(lambda n: n * 10, lst))
list(map(lambda n: (n, n * n), lst))
list(filter(lambda n : n % 2 == 0, lst))
from functools import reduce
reduce(lambda x, y : x * y, lst, 1)
```

**Evidencia - Terminal - Python**

![Evidencia - Terminal - Python](img/04-terminal-python-ipython.jpeg)

### Descripción general de los tres códigos

1. Declarar e inicializar una lista de números enteros.
2. Mapear: crear una nueva lista en donde cada elemento es fruto de la multiplicación por 10 de los elementos de la lista anterior.
3. Mapear: crear una nueva lista en donde cada elemento es una tupla que se genera con el elemento de la lista original y su cuadrado.
4. Filtrar los números que son pares.
5. Reducir: calcular el producto de los elementos que se encuentran en la lista.

### ¿Cuál de ellos tiene una sintaxis más fácil de comprender?

Luego de analizar las sintaxis de Java, Python y Scala, pude deducir que el lenguaje Scala es el más fácil de comprender, ya que las funciones de sus palabras reservadas son deducibles empíricamente, además de que se utilizan "flechas" que facilitan la lectura del código.

---

## Actividad N3

Transformar el siguiente código Java a Scala (se utilizó el texto [Scala 3, una breve iniciación](https://github.com/jorgaf/scala-3-intro/wiki/Scala-3,-una-breve-iniciaci%C3%B3n)).

```java
double getAverage(List<Integer> nums) {
	var sum = 0;
	for(var num : nums) {
		sum += num;
	}
	return sum / (double)nums.size();
}
```

### Respuesta

#### Scala - Estilo imperativo

```scala
//Código hecho por José Pablo Ramírez Jiménez
// Scala Imperativa
def getAvarage(nums: List[Int]): Double = {
	var suma: Double = 0.0
	for (i <- nums) {
		suma += i
	}
	var avarage = suma / nums.size
	avarage
}
```

**Evidencia - Terminal - Scala - Estilo imperativo**

Definición de la función:

![Evidencia - Terminal - Scala - Estilo imperativo (definición)](img/08-scala-imperativa-definicion.jpeg)

Llamada a la función:

![Evidencia - Terminal - Scala - Estilo imperativo (llamada)](img/07-scala-imperativa-llamada.jpeg)

#### Scala - Estilo funcional

```scala
//Código hecho por José Pablo Ramírez Jiménez
// Scala Funcional
def getAvarageFun(nums: List[Int]): Double = {
	nums.sum.toDouble / nums.size
}
```

**Evidencia - Terminal - Scala - Estilo funcional**

Declaración de la lista:

![Evidencia - Terminal - Scala - Estilo funcional (lista)](img/09-scala-funcional-lista.jpeg)

Definición y llamada a la función:

![Evidencia - Terminal - Scala - Estilo funcional (definición y llamada)](img/10-scala-funcional-llamada.jpeg)

#### Scala 3

La versión en Scala 3 corresponde a la solución desarrollada en el apartado anterior, [Scala - Estilo imperativo](#scala---estilo-imperativo) y [Scala - Estilo funcional](#scala---estilo-funcional).

#### Python

```python
# Python - Código hecho por IA
def get_average(nums: list[int]) -> float:
    return sum(nums) / len(nums)
```

**Evidencia - Terminal - Python**

![Evidencia - Terminal - Python (definición)](img/11-python-definicion.png)

![Evidencia - Terminal - Python (llamada)](img/12-python-llamada.png)

#### Haskell

```haskell
-- Haskell - Código hecho por IA
getAverage :: [Int] -> Double
getAverage nums = fromIntegral (sum nums) / fromIntegral (length nums)
```

**Evidencia - Terminal - Haskell**

*(Insertar aquí la captura de comprobación de la terminal de Haskell)*

---

**B1S1 - José Pablo Ramírez Jiménez**
