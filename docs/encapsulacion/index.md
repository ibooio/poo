---
layout: default
title: Encapsulación
nav_order: 5
---
## Encapsulación
La encapsulación consiste asegurar que las propiedades de los objetos solo sean accedibles y modificables mediante métodos provistos para tal fin. Desde el exterior solo debe poder accederse a  aquellos metodos que requieran ser accedidos, todos los demás no deberían de ser accesibles.

Por ejemplo, si un objeto posee un atributo peso este no debería de ser accesible desde fuera del objeto. Para dar acceso al mismo es necesario que el objeto posea un método que lo permita, lo mismo sucedería para la modificación.

### Visibilidad

Tanto para los atributos como para los métodos de una clase es posible definir limitaciones para su acceso. 

Existen tres grados de visibilidad que son, desde el menos al mas restrictivo:

#### public
Un atributo o método publico es visible y por ende accesible desde fuera del objeto, desde dentro y en el caso de la herencia es heredado por la subclase.
#### protected
Un atributo o método protegido es accesible solo desde una instancia de la clase(objeto) o de otra que herede de esta.
#### private
Un atributo o método privado solo es accesible desde dentro del objeto. Al aplicar herencia la subclase no hereda aquellos atributos que sean privados.

#### Ejemplo de Visibilidad
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
/* Podemos acceder al atributo edad porque este es público. No se cumple el principio de Encapsulacióm*/
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

### Ejemplo de encapsulación
```java
public class Personaje {

    /* Todos los atributos deben de ser private o protected en caso de que quisieramos 
    que fueran heredables */
    private String nombre;
    private int velocidad;

    public Personaje(String nombre, int velocidad) {
        this.nombre= nombre;
        this.velocidad= velocidad;
    }

    public String getNombre(){
        return this.nombre;
    };

    public void setNombre(String nombre){
        this.nombre = nombre;
    };

    public int getVelocidad(){
        return this.velocidad;
    };

    public void setVelocidad(int velocidad){
        this.velocidad = velocidad;
    };

    public void mover(){
        /* logica necesaria para mover el personaje */
    }

    private void calcularCansancio(){
        /* función privada que solo será accesible desde dentro del objeto */
    }

}

```