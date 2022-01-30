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

    public presentar(){
         System.out.println("Hola, me llamo " + this.nombre + " y tengo " + this.edad + "años");
    }
}
```
### Visibilidad

Tanto para los atributos como para los métodos de una clase es posible definir limitaciones para su acceso. 

Existen tres grados de visibilidad que son, desde el menos al mas restrictivo:

#### public
Un atributo o método publico es visible y por ende accesible desde fuera del objeto, desde dentro y en el caso de la herencia es heredado por la subclase.
#### protected
Un atributo o método protegido es accesible solo desde una instancia de la clase(objeto) o de otra que herede de esta.
#### private
Un atributo o método privado solo es accesible desde dentro del objeto. Al aplicar herencia la subclase no hereda aquellos atributos que sean privados.

#### Ejemplo
En el siguiente ejemplo se define la clase Persona. Esta posee tres atributos, cada uno con diferente visibilidad.  Además, hay tres métodos publicos(incluyendo el constructor y otro privado)

```java
public class Persona {

    private String nacionalidad;
    protected String nombre;
    public int edad;

    public Persona(String nombre, int edad) {
        this.nombre= nombre;
        this.edad= edad;
    }

    public setNacionalidad(String nacionalidad){
        this.nacionalidad = nacionalidad;
    };

    public presentar(){
        String saludo =  this.generarSaludo();
        System.out.println(saludo);
    }

    private generarSaludo(){
        return "Hola, me llamo " + this.nombre + " y tengo " + this.edad + "años. Mi nacionalidad es " + this.nacionalidad;
    }
}

/* Creamos un objeto de la clase Persona*/
Persona unaPersona = new Persona("Eva", 31);
/* Podemos acceder al atributo edad porque este es público.*/
System.out.println(unaPersona.edad);
/* Podemos llamar al método setNacionalidad porque es público */
unaPersona.setNacionalidad("argentina");
/* Podemos llamar al método presentar porque es público */
unaPersona.presentar();
/* Los atributos nacionalidad y nombre no son públicos, por ende
no podemos acceder a ellos. Lo mismo sucede con el método generarSaludo().
Sin embargo, el método presentar() hace uso del método generarSaludo()
y esto es posible porque cada objeto, internamente, puede acceder a todos sus atributos
y métodos independientemente de su visibilidad.
*/
```