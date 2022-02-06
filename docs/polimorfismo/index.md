---
layout: default
title: Polimorfismo
nav_order: 7
---
## Polimorfismo
El poliformiso es una concepto mediante el cual dos objetos de diferente tipo pueden realizar la misma acción y son en cierta forma intercambiables.

Este concepto está fuertemente ligado a la herencia y a las interfaces ya que estas permiten su implementación.

### Ejemplo
Supongamos que tenemos un clase Dispositivo de la que heredan las clases Computadora y Teléfono. Ambas sub clases implementan un método encender pero cada una lo hace a su manera.

```java

/* Si tuvieramos un metodo que espera un objeto de tipo Dispositivo */
public void unMetodo(Dispositivo dispositivo){
    dispositivo.encender();
}
/* Podriamos llamarlo tanto con un objeto Computadora como con uno Telefono */
Computadora computadora = new Computadora();
unMetodo(computadora);
Telefono telefono = new Telefono();
unMetodo(telefono);
/* 
Y en cada caso se utilizaría la implementación correspondiente del metodo encender.
Este concepto se conoce como Polimorfismo
 */

```

**
