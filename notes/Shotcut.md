---
title: Shotcut
created: '2020-01-09T07:58:06.271Z'
modified: '2020-01-13T09:43:40.295Z'
---

# Shotcut
--------------

Editor de vídeo gratuito para Linux

[//]: # (version: 1.0)
[//]: # (author: Iván Rodríguez)
[//]: # (date: 2020-01-09)

# Tabla de contenidos
1. [Enlaces Interesantes](#enlaces-interesantes)
2. [Instalar Shotcut](#instalar-shotcut)
3. [Uso Básico](#uso-básico)

## Enlaces Interesantes

- https://www.shotcut.org/ -> Página oficial de Shotcut
- https://youtu.be/ujdeOkz4TFY -> Curso de ShotCut (PodCast Linux)
- https://www.melodyloops.com/ -> Descargar de Musica ideal para vídeos

## Instalar Shotcut

#### Opción A) 
1. sudo apt install snapd                                   # Instalar Snap
2. sudo snap install shotcut                      

#### Opción B) (recomendada)
1. sudo apt install libsdl2-dev                             # Instalamos la libreria necesaria para Shotcut
2. sudo add-apt-repository ppa:haraldhv/shotcut             # Añadimos el repositorio oficial de Shotcut
3. sudo apt-get update
4. sudo apt install shotcut


## Uso Básico

### Unir Videos

1. Archivo > Abrir Archivos. 
Los elegimos por orden.
2. Ver > Linea de Tiempo
3. Arrastramos los vídeos de la lista de reproducción a la línea de tiempo
4. Juntamos los vídeos. Si ponemos uno sobre otro saldrá una transición (OJO, debe haber sgs de tiempo muerto)
5. Le damos a Archivo > Exportar Video.
6. Elegimos el Formato (por ejemplo mp4), y abajo pulsamos en [Exportar Archivo]
7. Escribimos un nombre (Ej: exportado.mp4) y le damos a [Guardar].
Habrá que esperar unos minutos en función de la duración del vídeo.

