
Los conceptos fundamentales en Java son:
	[Herencia](##Herencia)
	[Polimorfismo](##Polimorfismo)
	Abstracción
	Encapsulamiento

La unidad básica de encapsulamiento en Java es la clase. Encapsulamiento se refiere a contener codigo para que se ejecute. 

La clase **`Object`** es la superclase más alta en Java porque esta no se extiende a otra clase. En otras palabras, Object es la superclase de todas las demás clases en Java.

Esta clase, `Object`, hereda métodos muy útiles como `equals()` y `toString()`
- `equals()` → verifica si las variable hacen referencia al mismo objeto.
- `toString()` → da una representación string del objeto


La clases drivers se usan para controlar lo que sucede en el código. Estas suelen contener la función principal, `main()`.

Ejemplo de un driver:
```java
public class ShapeDriver
{
	public static void main(String[] args)
	{
		// Aqui va el código pricipal
	}

	// Aquí podemos declarar métodos del Driver
}
```

Se recomienda declarar las variables dentro de una clase como privadas. 

Cuando se declaran variables, les podemos asignar un acceso de miembro usando las palabras:  
- `Private` →  solo las puede acceder la clases en la que se declara
- `Protected` → solo puede acceder las clases de su mismo paquete
- `Public` → cualquier clase puede acceder

## Herencia

[La documentación de Java sobre Herencia](https://docs.oracle.com/javase/tutorial/java/IandI/subclasses.html)

### "Is a"

Usamos la expresión **"is a"** para describir la relación entre las superclases y subclases. Por ejemplo, la clase Rectangle **is a** Shape.

Para heredar de una clase, declaramos la clase así:
```java
package shapes; // states what package this driver belongs to
import java.awt.Color;

public class SubClase extends SuperClase
{
	private variable = 0;
	... //más codigo
}
```

El `extends` nos permite usar métodos y variables de la SuperClase.
Esta relación solo va en una dirección. En otras palabras, una ==SubClase puede usar métodos y valores de la SuperClase pero una SuperClase no puede acceder a los métodos o valores de la SubClase== .

Una subclase no hereda los constructores de la superclase, así que tocaría escribir los constructores de la subclase. Pero podemos usar la palabra reservada `super` para llamar al constructor de padre.

Ejemplo:
```java
public class Rectangle extends Shape
{
	private int length;
	private int width;

	// Constructor
	public Rectangle(String color, int l, int w)
	{
		super(color); // invoca el constructor Shape que inicializa la variable color
		this.lenght = l;
		this.width = w;
	}

	// Setters
	public void setLength(int l) { this.lenght = l; }
	public void setWidth(int w) { this.width = w; }
}
```

Otro ejemplo:
```java
public class Square extends Rectangle
{
	// Constructor
	public Square(String color, int size)
	{
		// invocamos al constructor de Rectangle
		super(color, size, size) 
		// el cuadrado es un rectangulo con el mismo length and width
	}
	
	// Para cambiar los valores del length y width del cuadrado
	public void setSize(int size)
	{
		//accede a los setters de la superclase Rectangle
		super.setLength(size);
		super.setWidth(size);
	}

}
```

### Overload y Override

**Sobrescribir un método (Override):**
   - Ocurre en una clase derivada (subclase) que hereda de una clase base (superclase).
   - Se utiliza la misma firma (nombre del método, tipo de retorno y lista de parámetros) que el método de la clase base.
   - El propósito es proporcionar una implementación específica en la subclase que reemplace la implementación en la superclase.
   - Se utiliza la anotación `@Override` para indicar explícitamente que estás sobrescribiendo un método.

   ```java
   class Animal {
       void hacerSonido() {
           System.out.println("Sonido genérico");
       }
   }

   class Perro extends Animal {
       @Override
       void hacerSonido() {
           System.out.println("Guau");
       }
   }
   ```

**Sobrecargar un método (Overload):**
   - Ocurre dentro de la misma clase (o en clases relacionadas, como una subclase).
   - Implica tener múltiples métodos con el mismo nombre en una clase pero con firmas diferentes (número o tipo de parámetros).
   - El compilador seleccionará el método correcto basándose en el número y tipo de argumentos en la llamada al método.

   ```java
   class Calculadora {
       int sumar(int a, int b) {
           return a + b;
       }

       double sumar(double a, double b) {
           return a + b;
       }
   }
   ```

En resumen, la ==sobrescritura está asociada con la herencia y la relación entre superclase y subclase==, mientras que la ==sobrecarga se refiere a tener múltiples versiones de un método con la misma nombre dentro de una clase==. 


### Applets

Un Applet en Java es un programa que se puede incorporar a un navegador en la web. La documentación de la clase Applet [esta disponible aquí](https://docs.oracle.com/javase/8/docs/api/java/applet/Applet.html)


## Polimorfismo

[Documentación en Java sobre polimorfismo](https://docs.oracle.com/javase/tutorial/java/IandI/polymorphism.html)

Polimorfismo es cuando una variable o referencia se puede referir a diferentes tipos de objetos. 

> 	Cuando se compila el código, Java no verifica que tipo (superclase o subclase) de objeto se encuentra dentro de una variable. Java abre el para ver que tipo de objeto esta dentro de la referencia de la variable e invoca a los métodos de ese tipo. 
> 	La distribución dińamica de un método (enlace dinámico) permite a Java saber de manera automática y correcta que método usar basado al tipo de referencia y objeto.

**Invalidación**
Es diferente a la sobrecarga de un método porque oculta el método de una superclase para que no pueda ser usado por una subclase a menos que use la palabra reservada `super`.
La invalidación no cambia los parámetros, solo la lógica.

## Abstracción

La abstracción se puede definir de varias formas. Nos centraremos en la idea de alejarnos de una función específica para adoptar una más general.

Piense en abstracción como el proceso de pasar de una tarea más específica a una tarea más general. Por lo tanto, en lugar de llamar a un constructor que siempre realice las mismas tareas, podríamos transferir valores que nos permitieran cambiar la configuración inicial.

- La abstracción tiene la finalidad de reducir la duplicación de información en un programa mediante el uso de abstracciones

- El principio de abstracción puede ser un concepto general como "no repetirse a sí mismo"

Una clase abstracta es aquella a la que no se le puede declarar una instancia. No se puede crear objetos de ese tipo. 

Se declaran usando la palabra `abstract`:
```java
public abstract class Bicycle
{
	// tambien se pueden declarar métodos abstractos
	abstract public void setPrice();

}
```

Para heredar de una clase abstracta:
- Se debe declarar al hijo como abstracto
- Se debe invalidar todos los métodos abstractos

- [I] Si esto no se hace se provoca un error de compilación 