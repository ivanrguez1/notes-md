---
title: ECMAScript 6
created: '2020-01-13T15:58:07.773Z'
modified: '2020-01-16T16:30:22.320Z'
---

# ECMAScript 6
--------------

[//]: # (version: 1.0)
[//]: # (author: Iván Rodríguez)
[//]: # (date: 2020-01-13)

# Tabla de contenidos
1. [Introducción](#introducción)

2. [Variables y Constantes](#variables-y-constantes)
  1.1. [Const](#const)
  1.2. [var](#var)
  1.3. [let](#let)

3. [Funciones](#funciones)
  3.1. [Funciones sobre funciones](#funciones-sobre-funciones)
  3.2. [Funciones Flecha](#funciones-flecha)

4. [Manejo Extendido de Parámetros](#manejo-extendido-de-parámetros)
  4.1. [Parámetros con valores por defecto](#parámetros-con-valores-por-defecto)
  4.2. [Operador extendido](#operador-extendido)

5. [Plantillas de Literales](#plantillas-de-literales)
  5.1. [Usar ${objeto.atributo}](#usar-objetoatributo)
  5.2. [Operar con ${objeto.atributo}](#operar-con-objetoatributo)
  5.3. [Intercalar cadenas con String.raw](#intercalar-cadenas-con-stringraw)
  5.4. [Conversiones](#conversiones)

6. [Propiedades de Objeto Mejoradas](#propiedades-de-objeto-mejoradas)
  6.1. [Definición de propiedades](#definición-de-propiedades)
  6.2. [Asignar parámetros a propiedades](#asignar-parámetros-a-propiedades)
  6.3. [Meter getter en el return](#meter-getter-en-el-return)
  6.4. [Crear atributos calculados](#crear-atributos-calculados)

7. [Desestructuración](#desestructuración)
  7.1. [Asignar valores de una lista a variables](#asignar-valores-de-una-lista-a-variables)
  7.2. [Asignación desde objetos](#asignación-desde-objetos)
  7.3. [Asignación desde funciones flecha](#asignación-desde-funciones-flecha)
  7.4. [Asignación con valores por defecto](#asignación-con-valores-por-defecto)
  7.5. [Asignación por parámetros de función, Array o por objeto](#asignación-por-parámetros-de-función-array-o-por-objeto)
  7.6. [Asignar una lista a variables ya definidas](#asignar-una-lista-a-variables-ya-definidas)
  7.7. [Intercambiar valores de variables](#intercambiar-valores-de-variables)

8. [Módulos](#módulos)
  8.1. [Uso de Export e Import](#uso-de-export-e-import)
  8.1. [Uso de Default](#uso-de-default)

9. [Clases](#clases)
  9.1. [Clases, constructores y métodos](#clases-constructores-y-métodos)
  9.2. [Herencia](#herencia)
  9.3. [Miembros estáticos](#miembros-estáticos)
  9.4. [Setter y Getter](#setter-y-getter)


## Introducción

[Tabla de contenidos](#tabla-de-contenidos)

- Nombres de los archivos
  1) Variables.html
  2) Funciones.html
  3) Parametros.html
  4) Literales.html
  5) Objetos.html
  6) This.html
  7) Desestructuracion.html
  8) Modulos.html
  9) Clases.html


- Para todos los ejemplos usaremos el siguiente código HTML:
```html
<!DOCTYPE html>
<html lang="es">
<head>
    <title>Título</title>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <style>
    </style>
</head>
<body>
    <script>
    </script>
</body>
</html>
```
- El código de JavaScript irá dentro de las etiquetas
```html
    <script>
    </script>
```

## Variables y Constantes

[Tabla de contenidos](#tabla-de-contenidos)

### const

- Recurso: http://www.etnassoft.com/2014/06/10/let-la-nueva-forma-de-declarar-variables-en-javascript/
- La palabra reservada const define una constante que no cambia

```javascript
        const PI = 3.141593;
        // PI = 10;     // Si intento reasignar la constante, la aplicación falla
        console.log("Valor de pi:" + PI);
```

### var

- Para definir variables globales, se empleará var

```javascript
        // Crear variable Global con var
        var i = 10;

        // Se puede usar una variable dentro del String con {variable} y usando tildes invertidas `
        console.log(`Valor var i: ${i}`);
```

### let

- Para definir variables locales (incluso dentro de iteraciones), se recomienda let

```javascript    
        // A) Crear variable local (no sale del for) con let
        // Si hubiesemos usado var i = 0, la i se saldría del contexto del for, "contaminando" el código
        for (let i = 0; i <= 2; i++) {
            console.log("Valor Let i: " + i);
        }

        

        // B) Además, con let podemos crear de un tirón variables de distinto tipo
        let
            // Tipo primitivo, como un booleano
            variablePrimitiva = new Boolean(true),

            // Un valor nulo
            variableNula = null,

            // Un array
            miArray = ['Hola', 'Mundo'],

            // Un Objeto
            camion = { marca: 'Volvo', modelo: 'FH16' },

            // Un Constructor, ojo, no confundir con el objeto
            // Obsérvese que los atributos son especificos (aunque los repitamos)
            miConstructor = function () {
                this.marca = 'Volvo';
                this.modelo = 'FH16';
            },

            // Una expresión de función invocada 
            funcionInvocada = (function () {
                let mostrar = function () {
                    console.info('Ejemplos de let');
                };

                return {
                    mostrar: mostrar
                }
            })();

        console.info(variablePrimitiva, variableNula, miArray, camion, new miConstructor(), funcionInvocada.mostrar()); 
```

## Funciones

[Tabla de contenidos](#tabla-de-contenidos)

### Funciones sobre funciones

- Se puede crear una función que ha su vez devuelva una función
- Recurso: https://medium.com/@sergiodxa/definiendo-conceptos-closure-y-scope-en-javascript-9081f1e113e6

```javascript  
  // CrearSuma crea a su vez otra función
  // Como funciona? sumar10(15) -> aplica 10 al parámetro a y 15 al parámetro b
  function crearSuma(a) {
      return function (b) {
          console.log("A=" + a);
          console.log("B=" + b);
          return a + b        // El último elemento NO necesita ;
      }
  }
  var sumar5 = crearSuma(5);
  var sumar10 = crearSuma(10);
  console.log(sumar5(15));
  console.log(sumar10(15));
```

### Funciones Flecha

- Mediante las funciones flecha, recortamos sintaxis, haciéndolo mas intuitivo.
- Pasamos de la función actual:
elementos.forEach(function (elemento) {...}
- A esto:
elementos.forEach(elemento => {...}


```javascript  
  // Funciones flecha
  // Recurso: https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Funciones/Arrow_functions

  var elementos = ["Hidrógeno", "Helio", "Litio"];

  // Sin la Función Flecha
  console.log(elementos.map(function (elemento) {
      return elemento.length;
  }));  // [9, 5, 5]

  // Con la Función Flecha
  console.log(elementos.map((elemento) => {
      return elemento.length;
  })); // [9, 5, 5]

  // Aún se puede recortar más...
  console.log(elementos.map(({ length }) => length)); // [9, 5, 5]

  // Función flecha (Otra opción)
  // Recurso: https://carlosazaustre.es/ecmascript6/
  // Para imprimir los elementos
  elementos.forEach(function (elemento) {
      console.log(elemento);
  });

  // Con la función flecha quedaria
  elementos.forEach(elemento => {
      console.log(elemento);
  });

  // Equivale a la forma clásica
  for (let i = 0; i < elementos.length; i++) {
      console.log(elementos[i]);
  }

```

## Manejo Extendido de Parámetros

[Tabla de contenidos](#tabla-de-contenidos)

### Parámetros con valores por defecto

- Recurso: http://es6-features.org/#DefaultParameterValues
- Podemos definir funciones con parámetros con valores por defecto
```javascript  
  function f1(x, y = 7, z = 42) {
      return x + y + z
  }
  console.log(f1(10))                         // Saca 10 + 7 + 42 = 59
```

### Operador extendido

- Añadir parámetros adicionales con un array de parámetros
  Para ello usaremos el operador extendido ...

```javascript  
  function f2(x, y, ...a) {
      return (x + y) * a.length
  }
  console.log(f2(1, 2, "hello", true, 7));    // Saca 3 * 3 (los elementos del array) = 9
                                              // "hello", true, 7 -> Los mete en el array [a]
```

- Un par de ejemplos más usando el operador extendido:

```javascript  
  // 3a) Operador extendido
  var parametros = ["Hola", true, 7]
  var otros = [1, 2, ...parametros];

  console.log(otros);

  // 3b) Podemos usarlo para convertir un String en array de caracteres
  var cadena = "camion";
  var caracteres = [...cadena];
  console.log(caracteres);

```

## Plantillas de Literales

[Tabla de contenidos](#tabla-de-contenidos)

- Recurso: http://es6-features.org/#StringInterpolation

### Usar &#36;&#123;objeto.atributo&#125;

```javascript  
// 
  // Podemos acceder a atributos de objetos con ${objeto.atributo}
  // Además, podemos crear cadenas multilínea
  var cliente = { nombre: "Iván" }
  var carro = { cantidad: 2, producto: "Palmera", precioUnitario: 1.60 }
  var mensaje =
      `Hola ${cliente.nombre},
      Quiere comprar ${carro.cantidad} ${carro.producto}s?
      El Precio Total es: ${carro.cantidad * carro.precioUnitario} €!`

  console.log(mensaje);
```

### Operar con &#36;&#123;objeto.atributo&#125;

```javascript  
  // Se puede operar sobre atributos/variables obtenidos con ${ }
  // Además, es fácil de concatenar cadenas...
  var cantidad1 = 10
  var cantidad2 = 5
  var producto = "turron"
  var url = `http://ejemplo.com/datos?cantidadTotal=${cantidad1 + cantidad2}&producto=${producto}`
  console.log(url);   // http://ejemplo.com/datos?cantidadTotal=15&producto=turron
```

### Intercalar cadenas con String.raw

```javascript  
    // Se pueden intercalar cadenas usando String.raw
    // Recurso: https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Objetos_globales/String/raw
    var cadenaRaw = String.raw({
        raw: ['Tengo ', ' camiones ', ' FH16']
    }, 2 + 3, ' Modelo ' + ' Volvo '); // 'foo5barJavaScriptbaz'
    console.log(cadenaRaw);
```

### Conversiones 

```javascript 
    // Podemos hacer conversiones 
    // Con 0b -> De Binario a entero
    // Con 0o -> De Octal a Entero
    console.log(0b111110111);       // Binario -> Entero = 503
    console.log(0o767);              // Octal -> Entero = 503
```

## Propiedades de Objeto Mejoradas

[Tabla de contenidos](#tabla-de-contenidos)

- Recurso: https://dev.to/sarah_chima/enhanced-object-literals-in-es6-a9d

### Definición de propiedades

```javascript  
  var marca = "Volvo", modelo = "FH16"
  camion = {
      marca,
      modelo
  }
  console.log(`Iván tiene un ${camion.marca}-${camion.modelo}`);
```

### Asignar parámetros a propiedades

```javascript  
  
  function crearCamion(marca, modelo, precio) {
      return {
          marca,
          modelo,
          precio
      }
  }
  console.log(crearCamion("Volvo", "FH16", 169900));
```

### Meter getter en el return

```javascript  
  // Podemos crear getter dentro del return
  // Obsérvese como NO hace falta pasar TODOS los parámetros. 
  // Por supuesto, podemos elegir el get que deseemos (pero el precio en este caso no...)
  function verCamion(marca, modelo, precio) {
      return {
          daMarca() { return marca },
          daModelo() { return modelo },
          daPrecio() { return precio }
      }
  }
  console.log(verCamion("Volvo", "FH16").daModelo())
```

### Crear atributos calculados

```javascript  

  // Podemos crear atributos calculados
  var atributo = "marca";
  var i = 0;
  const portatil = {
      [atributo + ++i]: "Asus",
      [atributo + ++i]: "Toshiba",
      [atributo + ++i]: "Lenovo"
  }

  console.log(portatil.marca1);       // "Asus"
  console.log(portatil.marca2);       // "Toshiba"
  console.log(portatil.marca3);       // "Lenovo"
```

## Uso de this

- Recursos:
  - https://blog.teamtreehouse.com/get-started-ecmascript-6
  - https://stackoverflow.com/questions/44895973/using-lexical-this-in-es6

- En la salida del objeto, por ejemplo dentro de una función toStringm, podemos emplear this para referirnos al propio objeto, mejorando la legibilidad del código.

```javascript  
  // Creo un objeto con los atribuitos nombre y coches
  // El this de coches/nombre se refiere al propio objeto
  let persona = {
      nombre: 'Iván',
      coches: ['Ferrari', 'Jaguar', 'Bugatti', 'Cadillac'],
      toString() {
          for (let coche of this.coches) {
              console.log(`${this.nombre} tiene un ${coche}`)
          }
      }
  }

  persona.toString();
```

## Desestructuración

[Tabla de contenidos](#tabla-de-contenidos)

- Recursos:
  - http://es6-features.org/#ArrayMatching
  - http://www.etnassoft.com/2016/07/04/desestructuracion-en-javascript-parte-1/
- La desestructuración es una técnica que permite sacar elementos desde listas (u objetos) y asignarlos a diversas variables de manera sencilla.

### Asignar valores de una lista a variables

```javascript  
  // Incluso podemos "saltarnos" uno o varios valores...
  var lista = [1, 2, 3]
  var [a, , b] = lista
  console.log(a)    // 1
  console.log(b)    // 3

  // La flexibilidad de JavaScript es tan potente que podemos asignar en una línea
  var [marca, modelo] = ['Volvo', 'FH16'];
  console.log(marca)
  console.log(modelo)
```

### Asignación desde objetos

```javascript  

  // La asignación la podemos hacer desde objetos
  var camion = {
      camionMarca: 'Volvo',
      camionModelo: 'FH16',
      camionPrecio: 169900
  };

  // MUY IMPORTANTE: Las variables deben llamarse IGUAL que los atributos del objeto
  // Si a la derecha hay menos elementos que a la izquierda, se desprecian (en este caso, pasamos del Precio)
  var { camionMarca, camionModelo } = camion;

  // Esta opción es perfectamente válida y funciona, pero es confusa
  // ({ camionMarca, camionModelo } = camion);
  console.info(camionMarca, camionModelo);    // Volvo FH16
```

### Asignación desde funciones flecha

```javascript  
  // Podemos asignar a partir de una función flecha
  var yoMismo = () => ['Iván', 'Rodríguez', 'Ruiz'];
  var [a, b, c] = yoMismo();
  console.info(a, b, c);                      // Iván Rodríguez Ruiz

  // Podemos crearnos una función que mapee los argumentos y los convierta, uno a uno, en mayúsculas
  // Luego aplicamos la función y las salidas las asignamos a sendas variables
  var mayusculas = (...argumentos) =>
      argumentos.map(
          valor => valor.toUpperCase()
      );

  var [d, e, f] = mayusculas('ejemplos', 'de', 'desestructuración');
  console.info(d, e, f);                      // EJEMPLOS DE DESESTRUCTURACIÓN
```

### Asignación con valores por defecto

```javascript  
  // Se pueden completar asignaciones con valores por defecto
  var objeto = { g: "valor1" }
  var lista = [10]
  var { g, h = 2 } = objeto
  var [i, j = "valor2"] = lista
  console.info(g, h, i, j);                   // valor1 2 10 valor2
```
### Asignación por parámetros de función, Array o por objeto 

```javascript  
  // Podemos asignar a través de parámetros de función, por Array o por objeto 
  function f1([nombre, valor]) {
      console.log(nombre, valor)
  }
  f1(["marca", "Volvo"])                      // marca Volvo

  function g1({ nombre: n, valor: v }) {
      console.log(n, v)
  }
  g1({ nombre: "modelo", valor: "FH16" })     // modelo FH16

  function h1({ marca, modelo }) {
      console.log(marca, modelo)
  }
  h1({ marca: "Volvo", modelo: "FH16" })
```

### Asignar una lista a variables ya definidas

```javascript  
  // Se puede asignar una lista a algunas variables YA definidas
  var lista2 = ["Ferrari", "Testarrosa"]
  var [k = 1, l = 2, m = "es", n = "miCoche"] = lista2
  console.info(k, l, m, n);                   // Ferrari Testarrosa es miCoche
```

### Intercambiar valores de variables

```javascript 
  // 8) Intercambiar valores de variables
  // Por supuesto, se puede pasar a la consola las variables con el formato ${variable}
  let o = 15, p = 25;
  [o, p] = [p, o];
  console.log(`${o} ${p}`);
  console.log(`${p} ${o}`);
```

## Módulos

[Tabla de contenidos](#tabla-de-contenidos)

- En los siguientes ejemplos veremos el uso de librerias externas (usando export/import)

### Uso de Export e Import
- Recurso: http://es6-features.org/#ValueExportImport

```javascript  
  // Recursos:
  // http://es6-features.org/#ValueExportImport

  // En librerias/Mates1.js, ponemos
  export function suma(x, y) { return x + y }
  export var pi = 3.141593

  // En Modulos.html ponemos:
  // MUY IMPORTANTE!! Para importar hay que tener un servidor configurado (como Apache)
  // Podemos realizar las importaciones de dos formas...
  // 1) Mediante un alias, sacando variables y funciones
  import * as mates from './librerias/Mates1.js';
  console.log("2π = " + mates.suma(mates.pi, mates.pi))

  // 2) Recoger variables y/o funciones 
  // OJO, el nombre debe ser igual al que viene en la libreria
  import { suma, pi } from "./librerias/Mates1.js"
  console.log("3π = " + suma(pi, 2 * pi))
```

### Uso de default
- Recurso: http://es6-features.org/#DefaultWildcard

```javascript  
  // En librerias/Mates2.js, ponemos:
  export var PI = 3.141593
  export var e = 2.71828182846
  export default (x) => Math.exp(x)

  // En Modulos.html ponemos:
  // Recurso: http://es6-features.org/#DefaultWildcard
  // 3) Marcar un valor como el valor exportado predeterminado y mezclar en masa los valores.
  import exp, { PI, e } from "./librerias/Mates2.js"
  console.log("e^{π} = " + exp(PI))

```

## Clases

[Tabla de contenidos](#tabla-de-contenidos)

- Se definen palabras reservadas para la POO.

### Clases, constructores y métodos
 
- Recursos: http://es6-features.org/#ClassDefinition
- Nuevas palabras reservadas: class y constructor

```javascript  
  // Creamos una clase con un constructor y un método
  // Lo instanciamos y lo escribimos por consola
  class Figura {
      constructor(id, posX, posY) {
          this.id = id
          this.mover(posX, posY)
      }

      mover(posX, posY) {
          this.posX = posX
          this.posY = posY
      }
  }

  const cuadrado = new Figura(1, 5, 7)
  // OJO a la comilla invertida
  console.log(`Cuadrado -> ID: ${cuadrado.id} - PosX: ${cuadrado.posX} - PosY: ${cuadrado.posY}`)
```

### Herencia

- Recursos: 
  - http://es6-features.org/#ClassInheritance
  - http://es6-features.org/#BaseClassAccess
- Nuevas palabras reservadas: extends y super

```javascript  
  // 2) Herencia: 
  // Usando la palabra reservada extends y super para acceder al constructor de la clase Base
  // IMPORTANTE: Figura está definida en el ejemplo anterior.
  class Circulo extends Figura {
      constructor(id, posX, posY, radio) {
          super(id, posX, posY)
          this.radio = radio
      }
  }
  const miCirculo = new Circulo(1, 4, 6, 10)
  // OJO a la comilla invertida
  console.log(`Circulo -> ID: ${miCirculo.id} - PosX: ${miCirculo.posX} - PosY: ${miCirculo.posY} - Radio: ${miCirculo.radio}`)
```

### Miembros estáticos

- Recursos:
  - https://developer.mozilla.org/es/docs/Web/JavaScript/Referencia/Classes/static
  - http://es6-features.org/#StaticMembers
- Son llamados sin necesidad de instanciar la clase

```javascript  
  // IMPORTANTE: Figura está definida en el ejemplo anterior.
  class Rectangulo extends Figura {
      constructor(id, posX, posY, ancho, alto) {
          super(id, posX, posY)
          this.ancho = ancho
          this.alto = alto
      }

      static rectanguloInicial() {
          return new Rectangulo(2, 0, 0, 100, 100)
      }
  }

  // Sin poner el New ya tenemos el Rectángulo
  var miRectangulo = Rectangulo.rectanguloInicial()
  console.log(`Rectangulo -> ID: ${miRectangulo.id} - PosX: ${miRectangulo.posX} 
  - PosY: ${miRectangulo.posY} - Ancho: ${miRectangulo.ancho}- Alto: ${miRectangulo.alto}`)
```

### Setter y Getter

Recurso: http://es6-features.org/#GetterSetter

```javascript  
  // Podemos definir Setter y Getter
  // IMPORTANTE: No podemos poner el mismo nombre para las funciones y los parámetros:
  // set ancho(ancho) { this.ancho = ancho }    // Da Error
  class Triangulo extends Figura {
      constructor(id, posX, posY, ancho, alto) {
          super(id, posX, posY)
          this.ancho = ancho
          this.alto = alto
      }
      set meterAncho(ancho) { this.ancho = ancho }
      get obtenerAncho() { return this.ancho }
      set meterAlto(alto) { this.alto = alto }
      get obtenerAlto() { return this.alto }
      get area() { return this.ancho * this.alto }
  }
  var miTriangulo = new Triangulo(3, 0, 0, 50, 20)
  console.log(`Triángulo -> Area: ${miTriangulo.area}`)
  console.log(`Triángulo -> Ancho: ${miTriangulo.obtenerAncho} - Alto: ${miTriangulo.obtenerAlto}  `)
```


```javascript  
  // 
```




