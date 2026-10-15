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

<img width="872" height="307" alt="01-sdkman-java" src="https://github.com/user-attachments/assets/2c532942-2604-4a45-bfb7-b82bdee5febc" />


### Instalación de sbt

```bash
sdk list sbt
sdk install sbt 2.0.10
```

**Evidencia**

<img width="872" height="73" alt="02-sdkman-sbt" src="https://github.com/user-attachments/assets/e681592d-0666-438b-a439-5901fcb703ef" />


### Instalación de Scala CLI

```bash
sdk list scalacli
sdk install scalacli 1.18.0
```

**Evidencia**

<img width="877" height="237" alt="03-sdkman-scalacli" src="https://github.com/user-attachments/assets/05ee754e-3adb-40e2-a96d-6aaeddb56ef7" />


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

<img width="677" height="247" alt="05-terminal-java-jshell" src="https://github.com/user-attachments/assets/644e9978-4f8f-4f4b-b91e-620eeee5ceac" />

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

<img width="550" height="207" alt="06-terminal-scala" src="https://github.com/user-attachments/assets/92c27473-3db8-4732-9121-04a69fce8a7f" />


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

<img width="505" height="212" alt="04-terminal-python-ipython" src="https://github.com/user-attachments/assets/39018205-9e4a-4795-8378-a03285f46761" />


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

<img width="481" height="200" alt="08-scala-imperativa-definicion" src="https://github.com/user-attachments/assets/b57eb2e2-85a5-4db5-8bee-36eb2153b870" />


Llamada a la función:

<img width="418" height="127" alt="07-scala-imperativa-llamada" src="https://github.com/user-attachments/assets/d74adc04-9eae-4b5a-9724-e4daa82171c6" />


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

<img width="340" height="67" alt="09-scala-funcional-lista" src="https://github.com/user-attachments/assets/dabe3e25-53aa-4c8a-8900-74521b08fd4f" />

Definición y llamada a la función:

<img width="462" height="147" alt="10-scala-funcional-llamada" src="https://github.com/user-attachments/assets/fb41f922-72df-4aa9-8dce-2f2b4cddfc92" />

#### Scala 3

La versión en Scala 3 corresponde a la solución desarrollada en el apartado anterior, [Scala - Estilo imperativo](#scala---estilo-imperativo) y [Scala - Estilo funcional](#scala---estilo-funcional).

#### Python

```python
# Python - Código hecho por IA
def get_average(nums: list[int]) -> float:
    return sum(nums) / len(nums)
```

**Evidencia - Terminal - Python**

<img width="605" height="143" alt="11-python-definicion" src="https://github.com/user-attachments/assets/414f4756-c400-4f9c-90e9-f4df891eec0c" />

<img width="265" height="62" alt="12-python-llamada" src="https://github.com/user-attachments/assets/c46daf83-8fb8-4a48-9a19-10b717d8415f" />


#### Haskell

```haskell
-- Haskell - Código hecho por IA
getAverage :: [Int] -> Double
getAverage nums = fromIntegral (sum nums) / fromIntegral (length nums)
```

**Evidencia - Terminal - Haskell**



---

**B1S1 - José Pablo Ramírez Jiménez**
