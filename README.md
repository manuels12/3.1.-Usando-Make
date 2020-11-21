# 3.1.-B3.1 Usando MAKE (de GNU) para automatizar la Terminal.
* * *
## MAKE (de GNU) para automatizar la Terminal  
GNU Make es una herramienta que controla la generación de ejecutables y otros archivos no fuente de un programa a partir de los archivos fuente del programa.

Make obtiene su conocimiento de cómo construir su programa a partir de un archivo llamado Makefile , que enumera cada uno de los archivos no fuente y cómo calcularlo a partir de otros archivos. Cuando escribe un programa, debe escribir un archivo MAKE para él, de modo que sea posible usar Make para construir e instalar el programa.

Capacidades de Make
Make permite al usuario final crear e instalar su paquete sin conocer los detalles de cómo se hace, porque estos detalles se registran en el archivo MAKE que usted proporciona.
Calcula automáticamente qué archivos necesita actualizar, según los archivos de origen que hayan cambiado. También determina automáticamente el orden correcto para actualizar los archivos, en caso de que un archivo que no sea de origen dependa de otro archivo que no sea de origen.
Como resultado, si cambia algunos archivos de origen y luego ejecuta Make, no es necesario volver a compilar todo su programa. Actualiza solo aquellos archivos que no son de origen y que dependen directa o indirectamente de los archivos de origen que modificó.

Make no se limita a ningún idioma en particular. Para cada archivo no fuente en el programa, el archivo MAKE especifica los comandos de shell para calcularlo. Estos comandos de shell pueden ejecutar un compilador para producir un archivo de objeto, el enlazador para producir un ejecutable, arpara actualizar una biblioteca o TeX o Makeinfo para formatear la documentación.
Make no se limita a crear un paquete. También puede usar Make para controlar la instalación o desinstalación de un paquete, generar tablas de etiquetas para él o cualquier otra cosa que desee hacer con la suficiente frecuencia como para que valga la pena escribir cómo hacerlo.
Crea reglas y objetivos
Una regla en el archivo MAKE le dice a Make cómo ejecutar una serie de comandos para construir un archivo de destino a partir de archivos de origen. También especifica una lista de dependencias del archivo de destino. Esta lista debe incluir todos los archivos (ya sean archivos de origen u otros destinos) que se utilizan como entradas para los comandos de la regla.


En este ejemplo utilizamos el siguiente codigo 
~~~
#Makefile
all: teclado
teclado: teclado.o
  ld -o $@ $+
teclado.o: teclado.s
  as -g -mfpu=vfpv2 -o $@ $<
clean:
  rm -vf teclado *.o
~~~
En el cual utilizamos MAKE para automatizar la terminal y nos dio como resultado: 

![](make.png)
En el cual agregue mi nombre y nos dio como resultado Hello Manuel 

