---
layout: default
title: Herencia
nav_order: 6
---
## Herencia

La herencia permite definir clases a partir de otras. Una clase que hereda de otra posee aquellos atributos y métodos heredables, y sobre esa base, puede extenderse con otros nuevos.

### Herencia simple

Se denomina herencia simple a aquella donde se hereda solo de una clase.

### Herencia multiple

La herencia multiple se da cuando una clase hereda de dos o mas clases. No todos los lenguajes admiten este tipo de herencia, entre ellos Java.

### Ejemplo de herencia simple
En el siguiente ejemplo se muestra la aplicación de herencia simple. Dos clases (Administrador y Visitante) heredan de otra(Usuario).

```java

public class Usuario {
    protected String email;
    protected String nombre;
    protected String apellido;

    public Usuario(String nombre, String apellido, String email){
        this.nombre = nombre; 
        this.apellido = apellido;
        this.email = email;
    }

    public String getNombre(){
        return this.email;
    }

    public String getApellido(){
        return this.email;
    }
    
    public String getEmail(){
        return this.email;
    }
}

/* 
    - La clase Administrador hereda de Usuario, por ende posee sus tres atributos y sus tres metodos
    - Dentro de su constructor, llama al constructor de la clase padre
    - Además, define una nueva propiedad (permisos) y un nuevo método(recuperarPermisos)
 */
public class Administrador extends Usuario{
    private List<Permiso> permisos;

    public Administrador(String nombre, String apellido, String email){
        super(nombre, apellido, email);
    }

    public void recuperarPermisos(){
        /*  metodo que permite recuperar un listado de permisos que tiene el usuario administrador */
        ...
    }
}

/* 
    - La clase Visitante hereda de Usuario, por ende posee sus tres atributos y sus tres metodos
    - Dentro de su constructor, llama al constructor de la clase padre
    - Además, define una nueva propiedad (mensajes) y un nuevo método(recuperarMensajes)
 */
public class Visitante extends Usuario{
    private List<Mensaje> mensajes;

    public Visitante(String nombre, String apellido, String email){
        super(nombre, apellido, email);
    }

    public void recuperarMensajes(){
        /* metodo que permite recuperar un listado de mensajes que recibió el usuario */
        ...
    }

}
```