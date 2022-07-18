# Informe-Circuito-Dimmer
En este informe se detalla el proceso para el montaje de un circuito Dimmer el cual controlará la potencia de un foco de 110V para corriente alterna 120V

## RESUMEN

Considerar conceptos en cuanto a corriente alterna, funcionamiento sobre DIAC y TRIAC, acompañada de un capacitor para poder controlar la potencia que ingresa en un foco de 110V, basándose en información sobre los circuitos funcionales que ya existen, añadir las resistencias necesarias para que el circuito sea funcional, complementar la información con ciertas nociones para comprender de dónde salen los datos de resistencias que ayudan a que el circuito sea estable.

## OBJETIVOS

### GENERAL

Analizar y comprender la información en base a los circuitos Dimmer ya existentes intuyendo el funcionamiento del mismo, teniendo nociones sobre el movimiento que traza la corriente alterna y las aplicaciones que se pueden obtener si deseamos aprovechar cierto voltaje en determinado tiempo.

### ESPECÍFICO

Implementar los componentes adecuados para el funcionamiento de un circuito Dimmer que sea capaz de controlar la potencia de un foco de 110V

## INTRODUCCIÓN

Dimmer viene del inglés, en su traducción al español es "regulador de intensidad" y sus aplicaciones son extensas y prácticas, siendo normal tener artefactos electrónicos los cuales se puedan regular su intensidad, entre estos un cautín, taladro, licuadora, focos, ventiladores, hornos y muchos otros. De manera técnica, el dimmer permite bajar el promedio de voltaje de una señal sinusoidal.

Los valores que se usan en el circuito a montar son basados en información previamente revisada y verificada, sin embargo, es importante conocer el origen de todos estos valores, siendo que todo se basa en la corriente alterna y artefactos regulables de 110V o 220V se añade el concepto de TAO (Constante del tiempo de circuito), se conoce que cinco TAO es suficiente para cargar al capacitor en cierto intervalo de tiempo (de 1ms a 30ms), tambien conocemos que:

Tao=resistencia*capacitor

Lo que resulta de calcular las resistencias necesarias en nuestro circuito, 10kΩ y 100Ω.

Estos conceptos en principio son suficientes para tener las nociones adecuadas para darle sentido al funcionamiento de nuestro circuito Dimmer.

## DESARROLLO

### MATERIALES

A continuación se presentan los materiales necesarios para que el circuito Dimmer pueda funcionar correctamente.

#### FOCO INCANDESCENTE

El circuito Dimmer controlará la potencia del foco, el cual será de 110V. Es necesario aclarar que este circuito puede funcionar con otros tipos de focos que respondan de la misma manera a la corriente alterna.

[![FOCO.jpg](https://i.postimg.cc/mZQmZfR9/FOCO.jpg)](https://postimg.cc/bdwxL5ZY)

#### POTENCIOMETRO 500kΩ//RESISTENCIA VARIABLE

Es una resistencia variable, es decir que aquel valor de la resistencia se puede modificar, posee tres terminales, positivo, negativo y controlador.

[![Potenciometro.jpg](https://i.postimg.cc/PxKn0L6X/Potenciometro.jpg)](https://postimg.cc/N9ynH0qS)

#### RESISTENCIA FIJA 10kΩ, 100Ω

Al contrario del potenciómetro, el valor de esta resistencia no varía, y sirve para proteger y ayudar al CAPACITOR a cargarse de manera correcta para que el DIAC pueda cerrar el TRIAC.

[![Resistencia-10k.jpg](https://i.postimg.cc/W19WRGVf/Resistencia-10k.jpg)](https://postimg.cc/FYLg3J7j)

#### TRIAC BT136

El triodo de corriente alterna o tiristor bidireccional, cambia la dirección o interrumpe el paso de la corriente eléctrica para el circuito de corriente alterna, por lo cual actúa como conmutador.

[![Triac.jpg](https://i.postimg.cc/65kgjL9V/Triac.jpg)](https://postimg.cc/crcF63t6)

#### DIAC DB3

El diodo de corriente alterna funciona como un diodo de disparo con una referencia de tensión fija es decir que permite pasar la corriente siempre y cuando se haya superado su tensión de disparo, no posee polaridad por lo cual es un tipo especial de diodo, posee dos terminales, se utilizan junto con TRIACS ya que controla el disparo del propio TRIAC, para controlar la potencia de un aparáto electrónico. La tensión máxima de ruptura es de 36V.

[![DIAC.jpg](https://i.postimg.cc/FFcBfkb7/DIAC.jpg)](https://postimg.cc/z3zj6Bcr)

#### CAPACITOR 104 100nF

El capacitor se encarga de almacenar energía eléctrica, esta energía es la que se necesita puntualizar para que funcione correctamente el DIAC, en el momento exacto en el que el capacitor se cargue pueda pasar aquel voltaje al DIAC y este se encargue de cerrar el TRIAC y aprovechar el promedio del voltaje deseado en instantes correctos del intervalo de la corriente alterna. 

[![CAPACITOR.jpg](https://i.postimg.cc/D0Vpj7hv/CAPACITOR.jpg)](https://postimg.cc/LYTVhKhw)

#### PROTOBOARD // CABLES (opcional)

Estos componentes son prescindibles, puesto que se desea entender de manera amena el circuito, el uso de la protoboard resulta útil, otorgando espacio y comodidad, igualmente se necesitan cables para poder hacer las conexiones.

[![Protoboard.jpg](https://i.postimg.cc/BvVVFxw1/Protoboard.jpg)](https://postimg.cc/f3YCn0sw)

### CIRCUITO DIMMER BASE

[![Esquema-Dimmer.png](https://i.postimg.cc/D0kFrVYs/Esquema-Dimmer.png)](https://postimg.cc/dkBzFfFt)

Tomado de electronicworld.com.mx

### FUNCIONAMIENTO

Con el circuito montado, podremos ver que si el potenciómetro se encuentra en su máxima resistencia, el flujo de corriente no es suficiente como para cargar al capacitor, una vez rotemos y disminuyamos la resistencia del potenciómetro la corriente podrá fluir hasta el capacitor, y aquí comienzan los procesos esenciales:

1) El capacitor se carga a 36V 
2) El DIAC permite el flujo de corriente.
3) El TRIAC se dispara cerrando el circuito y permitiendo pasar la corriente.
4) El voltaje de la corriente alterna se hará 0V y el TRIAC se abrirá.
5) El capacitor se carga a -36V
6) El DIAC permite el flujo de corriente.
7) El TRIAC se dispara cerrando el circuito y permitiendo pasar la corriente.
8) El voltaje de la corriente alterna se hará 0V y el TRIAC se abrirá.

Este proceso se repetirá siempre y cuando el potenciómetro permita un flujo de corriente adecuado y suficiente como para que el capacitor se pueda cargar.

### CONCLUSIONES

Los conocimientos que se requieren para poder entender el funcionamiento del circuito Dimmer en la corriente alterna puede ser algo complejo en un principio, pero indagando de manera correcta el comportamiento de cada componente, las fórmulas que se necesitaron para poder determinar un circuito tan necesario en nuestros días para poder controlar la potencia que consumimos, la electricidad se encuentra en todos lados y es imprescindible para facilitar la vida y optimizar todo aquello que usamos para obtener el máximo rendimiento.

### BIBLIOGRAFÍA

Circuito Dimmer o Regulador de tensión con triac. (2020, abril 23). Electrónica Básica. https://electronicabasica.site/circuito-dimmer-o-regulador-de-tension-con-salida-a-triac/

eMascaró. (2021, agosto 12). Qué es un dimmer y cómo funciona. Faro.es. https://faro.es/es/blog/que-es-un-dimmer-y-como-funciona/

Regulador de intensidad (DIMMER) con Triac y Diac. (2020, agosto 26). Electrónica para todos. http://www.electronicworld.com.mx/electronica/regulador-de-intensidad-dimmer-con-triac-y-diac/




