---
layout: default
title: Clases
nav_order: 2
---
## Clases
Las clases son las definiciones lógicas de los objetos. Contienen las especificaciones de los atributos y métodos que poseeran los objetos que se creen a partir de ellas.

En terminos simples, puede verse a las Clases como plantillas a partir de las cuales se crearan los objetos.

### Definición de una clase

Además de un nombre, las clases poseen definiciones de los atributos y métodos que tendrá cada instancia de ella. Existe un tipo especial de método llamado constructor y que tiene como finalidad construir una nueva instancia de la clase. 

### Constructores
Los métodos constructores son aquellos que permiten crear una instancia de una clase. Dentro de un constructor  puede definirse la lógica basica que debe ejecutarse en el momento de la creación de un objeto. En caso de que no se defina un constructor, la clase tendrá uno por defecto que no recibe argumentos.

Supongamos que la clase se llama Edificio, podremos instanciar un objeto de esta clase haciendo 
```java
Edificio miEdificio = new Edificio();
```
En caso de que la clase tenga un constructor que recibe una cadena como parametro, podremos instanciar un objeto de la siguiente manera
```java
Edificio miEdificio = new Edificio("Una cadena de caracteres");
```

### Atributos
Los atributos son... 

### Métodos
Los métodos son...

### Ejemplo
A continuación se define una clase Persona con dos propiedades(nombre y edad), un constructor y un método(presentar).

```java
public class Persona {

    private String nombre;
    private int edad;

    public Persona(String nombre, int edad) {
        this.nombre= nombre;
        this.edad= edad;
    }

    public void presentar(){
         System.out.println("Hola, me llamo " + this.nombre + " y tengo " + this.edad + "años");
    }
}
```