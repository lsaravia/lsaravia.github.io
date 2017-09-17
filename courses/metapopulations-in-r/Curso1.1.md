---
comments: true
title: "Metapoblaciones - 1.1"
author: "L.A. Saravia"
date: "12/2014"
output:
  slidy_presentation:
    duration: 180
    incremental: yes
  ioslides_presentation:
    incremental: yes
  beamer_presentation:
    incremental: yes
    pandoc_args: --latex-engine=xelatex
---

## Poblaciones

* Los organismos de un mismo grupo o especie, que viven en la misma zona geográfica

* ![](/images/Mar_del_Plata_playa.jpg)

* Y tienen la capacidad de entre-cruzamiento

* Tradicionalmente vistas como aisladas

    - Riesgo de extinción en función del tamaño
    - Las pequeñas poblaciones son susceptibles a las fuerzas exógenas 
    (depredación, parasitismo), estocasticidad (demográfica 
    y del medio ambiente), y a la depresión endogámica

## Las Poblaciones están conectadas


* ![](/images/ruta_2.jpg)

## Metapoblaciones

* Existe una estructura jerárquica en la naturaleza: 

* ![](/images/Hierarchy_nature06830.jpg)
    
    Las poblaciones son parte de redes de poblaciones conectadas por dispersión

## Ecología espacial

* Los paisajes pueden verse como redes de parches de hábitats con poblaciones locales
  
    ![](/images/SpatialEcology.png)

* La posición espacial de los individuos y poblaciones es importante
    - Influye en la tasa de crecimiento 
    - La dinámica de las interacciones: competencia, depredador-presa y huésped-parásito, mutualismos.

 

* Es bastante obvio para especies sésiles 
    ![](/images/SesilesAntarticas.jpg)

* Es menos obvio que la posición espacial es importante para especies móviles, que pueden tener un apareamiento mas o menos aleatorio (panmíctica).

* En especies de insectos las larvas son relativamente inmóviles y los adultos móviles. Las larvas tienen la mayoría de las interacciones y por lo que la distribución espacial de larvas influye en la dinámica  competitiva y depredador-presa.

* En algunas especies marinas las larvas suelen ser el estadío móvil y el adulto el sésil. 

## Cómo pasamos de poblaciones panmícticas a metapoblaciones

1. La dispersión puede no ocurrir en cada generación, los parches de microhábitat pueden tener poblaciones locales multigeneracionales.

    * El factor importante es la longevidad del microhábitat en relación con la duración de la vida de los individuos.

    * La dinámica de la metapoblación está determinada tanto por la estructura y la dinámica del entorno físico como por las propiedades de las especies.


2. La segunda forma de moverse al dominio metapoblación desde las poblaciones locales panmícticas es ampliando la escala espacial: la mayoría de los organismos tienen poderes limitados de dispersión

    * por lo tanto, hay una escala espacial a la cual la mayoría de las interacciones, incluyendo el apareamiento, se producen "dentro de las poblaciones"

    * mientras que a grandes escalas espaciales, estas poblaciones locales están conectados por la migración y el flujo de genes.





## Un ejemplo en mariposas: *Melitaea cinxia* 

* Se encuentra ampliamente distribuida en toda Europa y Asia, pero sólo reproduce
en prados abiertos. 

* En las islas Aland de Finlandia, la Glanville fritillary se encuentra sólo en pequeñas praderas que contienen una o ambas de las dos especies de plantas, Plantago lanceolata y Veronica spicata, que sirven como anfitriones a la mariposa en su etapa larval. 

    [Hanski (2011) Eco-evolutionary spatial dynamics in the Glanville fritillary butterfly.](http://www.pnas.org/content/108/35/14397).


* Debido al pequeño tamaño de estos prados, las poblaciones de la Glanville fritillary se extinguen de forma rutinaria

* La especie existe en un delicado equilibrio entre la extinción y recolonización de otros parches


## El hábitat de *Melitaea cinxia* 

* <center> 
  ![](/images/GlanFritMap.png) 
  </center>

   Mapa de la red de parches de hábitat en las islas Åland que indica la relativa abundancia de V. spicata en los prados (color más oscuro indica una mayor abundancia relativa de Verónica; valores promedio en 1993-2010). Sombreado gris muestra la tierra, y el resto es mar.

## Extinción y recolonización de *Melitaea cinxia*

* ![](/images/GlanFritA.png)
    
    Tamaño de Metapoblación se cuantifica como el número de grupos de larvas
    donde los prados pueden contener 1 a 150 grupos de larvas, cada uno de los cuales es el resultado de una sola nidada de huevos.

* ![](/images/GlanFritB.png)
  
    Número de extinciones y colonizaciones entre ≈ 1.600 prados encuestados entre 1993-2010. 

* ![](/images/GlanFritC.png)
    
    Las extinciones y colonizaciones de (B) vs ocupación de parches para el mismo período.

## Ejercitación 

* Encontrar ejemplos de metapoblaciones y exponerlos


    
## El proceso de modelación

![](/images/ModelingProcess.png){: .align-center}

## Identificar la cuestión ecológica

* Habría que saber que es lo que queremos encontrar antes de empezar a buscar y a tratar de modelar. 

    1. La pregunta debería formularse tanto a nivel conceptual general ("La estructura metapoblacional influencia en los factores de extinción") y a un nivel específico ("La cantidad de extinciones y colonizaciones sería la misma si tuviera un solo gran parche").

    2. Es bueno formular preguntas alternando entre estos dos niveles, ser demasiado vaga ("Quiero explorar las metapoblaciones") o demasiado específico ("¿cuál es la diferencia en las pendientes de estas dos regresiones lineales?") puede impedir su progreso.

    3. En un mundo ideal uno debería identificar las cuestiones ecológicas antes de diseñar tus experimentos o toma de datos. Pero muchas veces sucede lo contrario: ya se tienen los datos y hay que ver que se puede responder con ellos.

## Elección del modelo

* **El modelo determinista**: Hay que elegir una descripción matemática del patrón que está tratando de 
    describir. La parte determinista es el promedio, o el patrón esperado en la ausencia de cualquier tipo de aleatoriedad o error de medición.

* **El modelo estocástico**: con el fin de estimar los parámetros de un modelo, lo que necesita saber no sólo el patrón esperado, sino también algo acerca de la variación con respecto al patrón esperado.Típicamente, usted describe el modelo estocástico especificando una distribución de probabilidades razonable para la variación.

## Ajustar parámetros

* Una vez que haya definido su modelo, puede estimar tanto los parámetros deterministas (pendientes, tasas, tiempos de extinción ) Y los parámetros estocásticos (la varianza o los parámetros de controlan  la varianza). 

* Este paso es un ejercicio puramente técnico, pero requiere una visión biológica/ecológica al inicio para tener una idea de valores razonables de parámetros y al final porque los parámetros ajustados son esencialmente las respuestas a tu pregunta.

## Estimar intervalos de confianza / probar hipótesis / selección de modelos

* No alcanza con el conjunto de parámetros que mejor ajustan (las estimaciones puntuales, en la jerga estadística). 

* Sin alguna medida de la incertidumbre, estas estimaciones no tienen sentido. Al cuantificar la incertidumbre en el ajuste de un modelo, se puede calcular los límites de confianza para los parámetros.

* También puede probar hipótesis ecológicas, desde un punto de vista estadístico tanto como ecológico 
    
    + por ejemplo: podemos cuantificar la diferencia estadística entre tasas de colonización a distintas temperaturas

    + son estas diferencias lo suficientemente grandes como para influir en la dinamica de la metapoblación?

* También es necesario cuantificar la incertidumbre a fin de elegir el mejor de un conjunto de modelos, o para decidir cómo ponderar las predicciones de diferentes modelos.

## Responder a las preguntas / volver al paso 1

* **El modelado es un proceso iterativo**: Es posible que haya respondido a sus 
preguntas con una sola pasada a través de los pasos 1-5, pero es probable que la estimación de los parámetros y límites de confianza le obligara a redefinir sus modelos (que cambian su forma o complejidad o las covariables ecológicos que tienen en cuenta) 

* Incluso a redefinir sus cuestiones ecológicas originales. Puede que tenga que hacer preguntas diferentes, o recoger otro conjunto de datos, para entender mejor cómo funciona su sistema.

## Referencias

1. [Hanski IA, Gaggiotti OE (2004) Ecology, Genetics and Evolution of Metapopulations. Academic Press.](https://drive.google.com/file/d/0BzexxHVKtpiAVDQwSHhWZ0dvQ2M/view?usp=sharing)

1. Hanski IA (2011) Eco-evolutionary spatial dynamics in the Glanville fritillary butterfly. Proc Natl Acad Sci 108: 14397–14404. doi:10.1073/pnas.1110020108.

1. [Bolker B (2008) Ecological Models and Data in R. Princeton University Press.](https://drive.google.com/file/d/0BzexxHVKtpiAQjhBRDdZQW51WlU/view?usp=sharing)