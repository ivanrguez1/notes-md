---
attachments: [Clipboard_2020-02-06-13-28-13.png, Clipboard_2020-02-06-13-28-14.png, Clipboard_2020-02-06-13-40-07.png, Clipboard_2020-02-06-13-40-08.png, Clipboard_2020-02-06-13-49-12.png, Clipboard_2020-02-06-13-49-13.png, Clipboard_2020-02-06-13-57-43.png, Clipboard_2020-02-06-13-57-44.png, Clipboard_2020-02-06-14-45-17.png, Clipboard_2020-02-06-14-45-19.png, Clipboard_2020-02-06-14-46-49.png, Clipboard_2020-02-06-14-46-50.png, Clipboard_2020-02-07-08-59-03 (2).png, Clipboard_2020-02-07-08-59-03.png, Clipboard_2020-02-07-09-46-41.png, Clipboard_2020-02-07-09-46-42.png, Clipboard_2020-02-07-11-10-52.png, Clipboard_2020-02-07-11-10-53.png, Clipboard_2020-02-07-11-23-19.png, Clipboard_2020-02-07-11-23-20.png, Clipboard_2020-02-07-11-51-00.png, Clipboard_2020-02-07-11-51-01.png, Clipboard_2020-02-07-11-58-46.png, Clipboard_2020-02-07-11-58-47.png, Clipboard_2020-02-07-12-05-48.png, Clipboard_2020-02-07-12-05-49.png, Clipboard_2020-02-07-12-11-45.png, Clipboard_2020-02-07-12-11-46.png]
title: OpenShot
created: '2020-02-06T10:05:39.616Z'
modified: '2020-03-05T08:51:11.908Z'
---

# OpenShot
--------------

Editor de vídeo gratuito para Linux

[//]: # (version: 1.0)
[//]: # (author: Iván Rodríguez)
[//]: # (date: 2020-02-06)

# Tabla de contenidos
1. [Enlaces Interesantes](#enlaces-interesantes)
2. [Instalar OpenShot](#instalar-openshot)
3. [Tutorial Rápido](#tutorial-rápido)
4. [Opciones Generales](#opciones-generales)
  4.1. [Partes de la Interfaz](#partes-de-la-interfaz)
  4.2. [Tutorial incorporado](#tutorial-incorporado)
  4.3. [Pistas y capas](#pistas-y-capas)
  4.4. [Dividir Clip](#dividir-clip)
  4.5. [Añadir a la línea de tiempo](#añadir-a-la-línea-de-tiempo)
  4.6. [Propiedades del archivo](#propiedades-del-archivo)
5. [Clips](#clips)
  5.1. [Menú asociado](#menú-asociado)
  5.2. [Efectos](#efectos)
6. [Transiciones](#transiciones)
  6.1. [Propiedades de la Transición](#propiedades-de-la-transición)
  6.2. [Transiciones personalizadas](#transiciones-personalizadas)

## Enlaces Interesantes

- https://www.openshot.org/es/
- https://www.acapela-group.com/demos/ &rightarrow; Sintetizador de voz para audios

## Instalar OpenShot

[Tabla de contenidos](#tabla-de-contenidos)

```console
sudo add-apt-repository ppa:openshot.developers/ppa
sudo apt-get update
sudo apt-get install openshot-qt
```

## Tutorial Rápido

[Tabla de contenidos](#tabla-de-contenidos)

Vamos a hacer un pequeño tutorial de 5min para crear un vídeo a partir de varias imágenes y música.

- Vamos a seguir este procedimiento:
https://cdn.openshot.org/static/files/user-guide/quick_tutorial.html

1. Para empezar nos bajaremos música y fotos para hacer el vídeo:
  - https://www.soundboard.com/sb/Star_trek_theme_song
    - https://www.soundboard.com/sb/sound/369585 > [Download Sound]
  - https://wall.alphacoders.com/by_sub_category.php?id=231559&name=Star+Trek%3A+Enterprise+Fondos+de+pantalla&lang=Spanish
    - https://images.alphacoders.com/789/789962.jpg
    - https://images7.alphacoders.com/667/667383.jpg
    - https://images6.alphacoders.com/789/789970.jpg
    - https://images5.alphacoders.com/789/789965.jpg
    - https://images5.alphacoders.com/789/789966.jpg

2. Arrastramos las imágenes y la música a la sección de Archivos del proyecto.
3. Ahora hacemos lo mismo desde los archivos del proyecto hasta la línea de tiempo en la zona inferior de la aplicación. Si pulsamos en cada imagen podremos aumentar el tiempo que dura en la reproducción.
4. En cualquier momento podemos mover el selector de punto de reproducción para ver qué es lo que se ve en un momento determinado:

![](@attachment/Clipboard_2020-02-06-13-28-13.png)
![](attachments/Clipboard_2020-02-06-13-28-14.png)

5. Arrastramos el archivo de música de la sección de archivos del proyecto a la línea de tiempo (por ejemplo a la pista2)
6. Cuadramos los tiempos para que coincida el fin de las imágenes con el de la música...
7. Algo que también podemos hacer es crear transiciones. Para ello arrastramos una imagen ligeramente por encima de otra que tenga a la izquierda, dejando un hueco azul claro.

![](@attachment/Clipboard_2020-02-06-13-40-07.png)
![](attachments/Clipboard_2020-02-06-13-40-08.png)

8. Por último exportamos el vídeo con CTRL+E o Archivo > Exportar vídeo o bien pulsando el botón del círculo rojo situado a la derecha del menú ayuda. Nos aparece la ventana de exportar vídeo donde podemos configurar dónde vamos a poner la salida del vídeo, el formato o la calidad. Pulsamos en [Eportar Vídeo]

![](@attachment/Clipboard_2020-02-06-13-49-12.png)
![](attachments/Clipboard_2020-02-06-13-49-13.png)

9. Para acabar, guardamos el proyecto: Archivo > Guardar Proyecto.


## Opciones Generales.

### Partes de la Interfaz.

[Tabla de contenidos](#tabla-de-contenidos)

Al iniciar la aplicación vereemos lo siguiente:
![](@attachment/Clipboard_2020-02-06-13-57-43.png)
![](attachments/Clipboard_2020-02-06-13-57-44.png)

Las distintas partes de la interfaz son:
1. Barra de herramientas principal
2. Pestañas de funciones
3. Archivos de proyecto
4. Ventana de vista previa
5. Barra de herramientas Editar
6. Zoom de la línea de tiempo
7. Escala de tiempo / Cabezal de reproducción
8. Cronograma (Línea de tiempo)
9. Filtrar


### Tutorial incorporado

[Tabla de contenidos](#tabla-de-contenidos)

Al iniciar la aplicación por primera vez nos aparecerá un tutoial. De todos modos podemos volver a verlo desde:
. Ayuda > Tutorial


### Pistas y capas.

[Tabla de contenidos](#tabla-de-contenidos)

Es fundamental entender que las pistas del cronograma funcionan como capas, solapándose unas con otras. La capa que esté por encima tapará a la de abajo.
OJO! La numeración de las capas o su nombre NO DETERMINA si será visible o no (de hecho podemos cambiar su nombre)
Lo que si lo determina es la posición en el cronograma: las capas superiores TAPAN a las capas inferiores.


### Dividir Clip.

[Tabla de contenidos](#tabla-de-contenidos)

Muchas veces tendremos que editar un video que YA está realizado. Por ejemplo, usando OBS. Pues bien, en primer lugar es buena idea dividir dicho vídeo en escenas y darle los efectos deseados. Para ello existe la opción de Dividir Clip.

1. Nos bajamos este archivo:
  - http://clips.vorwaerts-gmbh.de/big_buck_bunny.mp4
2. Creamos un proyecto nuevo (Archivo > Proyecto Nuevo)
3. Importamos el vídeo y le damos botón derecho > Dividir el clip..

![](@attachment/Clipboard_2020-02-06-14-46-49.png)
![](attachments/Clipboard_2020-02-06-14-46-50.png)

4. Elegimos el [Inicio], arrastramos el selector de tiempo y pulsamos en [Fin]. En nombre ponemos por ejemplo Escena1 y le damos a [Crear]:
NOTA: Los valores son aproximados 
  - 00:00 - 11:20 &rightarrow; Escena1
  - 11:20 - 15:25 &rightarrow; Escena2
  - 15:25 - 23:00 &rightarrow; Escena3
  - 23:00 - 31:00 &rightarrow; Escena4
  - 33:00 - 48:00 &rightarrow; Escena5
  - 48:00 - 1:00:00 &rightarrow; Escena6

Seguimos en el siguiente apartado...

### Añadir a la línea de tiempo.

[Tabla de contenidos](#tabla-de-contenidos)

Podemos agregar varios archivos a la línea de tiempo (y no uno por uno como ya vimos).
Para ello nos vamos a la sección de Archivos del proyecto, seleccionamos varios clips (todos los que creamos en el apartado anterior, omitiendo el original) y le damos al botón derecho > Añadir a la línea de tiempo (o directamente con CTRL + W).

![](@attachment/Clipboard_2020-02-07-09-46-41.png)
![](attachments/Clipboard_2020-02-07-09-46-42.png)

Entre las opciones que podemos elegir están:
- Tiempo de Inicio, punto inicial de inserción en la línea de tiempo.
- Pista donde se agregan los clips.
- Atenuación (Dentro, fuera o ambos)
- Zoom de los clips
- Transición (el mismo se aplica a los espacios entre clips)

### Propiedades del archivo.

[Tabla de contenidos](#tabla-de-contenidos)

Podemos ver, dentro de la sección Archivos del Proyecto, las propiedades de un elemento concreto. Para ello pulsamos el botón derecho sobre un archivo y le damos a Propiedades.

![](@attachment/Clipboard_2020-02-07-11-10-52.png)
![](attachments/Clipboard_2020-02-07-11-10-53.png)


## Clips.

[Tabla de contenidos](#tabla-de-contenidos)

Cada archivo multimedia agregado a la línea de tiempo se denomina clip.
Un clip tiene una serie de propiedades esenciales que son:
- Escala (X,Y)
- Ubicación (Posición X, Posición Y)
- Rotación (en grados)
- Alfa (Transparencia)
Y otras propiedades adicionales.

Para visualizar las propiedades de un clip, pulsamos el botón derecho sobre un clip de la línea de tiempo y pulsamos en Propiedades.
![](@attachment/Clipboard_2020-02-07-11-23-19.png)
![](attachments/Clipboard_2020-02-07-11-23-20.png)


### Menú asociado.

[Tabla de contenidos](#tabla-de-contenidos)

En cada clip, al pulsar el botón derecho en la línea de tiempo, encontraremos un menú asociado con todas las acciones que se pueden realizar sobre él.
Algunas de estas las veremos mas adelante.

![](@attachment/Clipboard_2020-02-07-11-51-00.png)
![](attachments/Clipboard_2020-02-07-11-51-01.png)


### Efectos.

[Tabla de contenidos](#tabla-de-contenidos)

Podemos aplicar distintos efectos al clip pulsando en la pestaña Efectos, situada junto a la de Archivos del proyecto. Para aplicar un efecto, bastará con elegirlo y arrastralo sobre el clip deseado en la línea de tiempo.

![](@attachment/Clipboard_2020-02-07-11-58-46.png)
![](attachments/Clipboard_2020-02-07-11-58-47.png)



## Transiciones.

[Tabla de contenidos](#tabla-de-contenidos)

Una transición es un efecto que se desvanece (o borra) entre dos clips.
Hay dos formas de crear transiciones:
1. Arrastrar un clip sobre otro (por ejemplo metemos uno detrás de otro las escenas 3 y 4 del apartado 4.4.)
2. Ponemos ambos clips y luego elegimos la transición en la pestaña de Transiciones.
En el siguiente apartado veremos una captura con un ejemplo de transición.

### Propiedades de la Transición.

[Tabla de contenidos](#tabla-de-contenidos)

Podemos invertir el proceso de transición pulsando el botón derecho sobre la transición en el cronograma y haciendo clic en Invertir Transición.
Además, podemos QUITAR la transición eligiendo en el mismo punto Quitar transición o simplemente haciendo clic y pulsando en [SUPR].

![](@attachment/Clipboard_2020-02-07-12-11-45.png)
![](attachments/Clipboard_2020-02-07-12-11-46.png)

Por otro lado, al seleccionar la transición en el cronograma, tendremos en la sección de propiedades (situada en el lado izquierdo de la interfaz) aquellas características modificables de la transición.

### Transiciones personalizadas.

[Tabla de contenidos](#tabla-de-contenidos)



### .

[Tabla de contenidos](#tabla-de-contenidos)













  
