# Selector de atributos y colision de estilos CSS
----------------
>

> **Selectores  adyacentes elemento1 + elemento2**
Dice que todos los elementos(n) seguidos de elemento1 heredan los estilos 
el elemento1 no heredará ni tendrá los estilos de los elementos hermanos puesto
que no tiene un elemento de su mismo tipo atrs de el:

``` css
p+p{
    color:red
}
```
> **Selectores hijos ePadre > eHijos** todos los elementos directamente hijos
del elmeento padre heredan los estilos, los elementos hijos son solo los que estan dentro de su scope
 
``` css
 ePadre > eHijo {
    color:red
 }
```
``` html
 <ePadre>
    <eHijo>
        Hijo 1
    </eHijo>
    <eHijo>
        Hijo 2
    </eHijo>
    <p>
        <eHijo>
            "Este no es hijo de <ePadre>"
        </eHijo>
    </p>
 </ePadre>
```

> **Selectores hermanos h ~ h** Todos los hermanos menores de un elemento
aunque esten separados  por otros elementos, se considera que es un hermano
cuando vive en la misma ruta que el elemento hermano
 
``` css
p ~ p{
    color:red
}
```
> **Selectores para elmentos que contengan {}** Estos estilos se agregan
a elmentos que contienen cierto tipo de argumentos ó cierto
tipo de elmentos que contienen un argumento con algun valor

* HTML
``` html
/*Elementos que contienen un argumento*/
<h2 title="cascada"> Texto en H2</h2>
```
* CSS
``` css
/*Elementos que contienen un argumento*/
h2[title]{
    color:red;
}

/*Elementos que su argumento = <valor> (sea igual a)*/
h2[title="main"]{
    color:red;
}

/*Elementos que contienen un argumento (que solo contenga ese argumento )*/
h2[title ~="ai"]{
    color:red;
}
```
---------
> gerarquia de colision de estilos, los estilos se van aplicando conforme
el orden de la siguiente lista


    1- css del navegador
    2- css del usuario
    3- archivos css enlazados en el orden añadidos
    4- propiedades que se heredan
    5- propiedades propias del elemento
    6- clases asignadas, y en el mismo orden
    7- identificador
    8- !important