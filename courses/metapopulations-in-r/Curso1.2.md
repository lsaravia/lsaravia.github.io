---
comments: true
title: "Metapoblaciones - 1.2"
author: "L.A. Saravia"
date: "12/2014"
output:
  slidy_presentation:
    duration: 60
    incremental: yes
  ioslides_presentation:
    incremental: yes
  beamer_presentation:
    incremental: yes
    pandoc_args: --latex-engine=xelatex
---

## El lenguaje R 

+ Como instalar R para cualquier Sistema Operativo ver 

	<http://cran.r-project.org/>

+ Instalar R para windows
	
	<http://cran.r-project.org/bin/windows/base/>

+ Instalar R para Linux (ubuntu trusty)
		
		lsb_release -a
		sudo add-apt-repository "deb http://cran.stat.ucla.edu/bin/linux/ubuntu precise/"
		sudo apt-get update
		sudo apt-get install r-base

+ Instalar *RStudio*

	<http://www.rstudio.com/ide/download/desktop>


## Empezar con *RStudio* 

+ Primero cargar RStudio

+ RStudio tiene cuatro paneles 

	1. Abajo a la izquierda - este es el intérprete de R. Si escribe código aquí, es "evaluado" por lo que se obtiene una respuesta.

	2. Arriba a la izquierda - editor para escribir piezas más largas de código.

	3. Arriba a la derecha - Se encuentran los objetos del espacio de trabajo. En la solapa History estan los comandos que ingresamos previamente. 

	4. Abajo a la derecha - Mostrará archivos, gráficos, paquetes instalados, y la ayuda.

## Usar R como una calculadora

+ Probemos

		1 + 100

		[1] 101

		3 + 5 * 2 ^ 2

		[1] 23

		(3 + 5) * 2

		[1] 16

+ Escribiendo ?palabra  entra al sistema de ayuda 

		?Arithmetic

		?"+"

+ Operadores lógicos

		1 == 1  

		[1] TRUE
			

		1 != 2  


		[1] TRUE

		1 <  2  

		[1] TRUE

		1 <= 1  

		[1] TRUE

		1 >  0  

		[1] TRUE

		1 >= -9 

		[1] TRUE

		?Comparison
		help("==") 

+ Notacion científica


		2/10000


		[1] 2e-04

## Funciones matemáticas

+ R tiene las funciones usuales

		sin(1)  # trig functions

		[1] 0.8415

		asin(1) # inverse sin 

		[1] 1.571

		log(1)  # natural logarithm

		[1] 0

		log10(10) # base-10 logarithm

		[1] 1

		log2(100) # base-2 logarithm

		[1] 6.644

		exp(0.5) # e^(1/2)

		[1] 1.649

	Ver pagina 39 del libro de [Crawley](https://drive.google.com/file/d/0BzexxHVKtpiAaGJwMng5WTNveEk/view?usp=sharing)

## Asignacion de variables

+ Qué es una variable?

+ Se utiliza el operador <-

		x <- 1/40

		x

		[1] 0.025

+ La variable no contiene la fraccion 1/40, contiene la aproximación decimal de esta fracción. En este 
	caso parece exacta pero no lo es. Estas aproximaciones decimales se llaman "números de punto flotante".

+ En el panel superior derecho "workspace" apareció la variable x, allí aparecen todos los elementos que pueden ser usados en el espacio de trabajo.

		log(x)


		[1] -3.689


		sin(x)

		[1] 0.025

+ La asignación no imprime un valor 

		x <- 100

+ Las variables pueden ser reasignadas (por eso son variables). Y pueden contener la misma u otra variable:

		x <- x + 1

+ La asignación procede evaluando de derecha a izquierda.

+ Los nombres de variables pueden tener letras, números, guiones bajos, puntos. No pueden comenzar con un número y no pueden tener espacios, y son sensitivas a las mayúsculas.

		variable_1.dia2

	es distinta que

		Variable_1.dia2

		variableConSeparacionDeMayusculas

	Ver página 40 del libro de [Crawley](https://drive.google.com/file/d/0BzexxHVKtpiAaGJwMng5WTNveEk/view?usp=sharing)

## Ejercicio 1


* Calcule la diferencia en años entre el momento actual y el año que inició en la Universidad. Divida este por la diferencia entre ahora y el año en que usted nació. Multiplique esto por 100 para obtener el porcentaje de su vida que desperdició en la universidad. Utilice paréntesis si los necesita, utilice la asignación si la necesita.

* Y si quiere saber cuantos dias hace desde que nació? Ayuda: ver ?as.Date

## Tipos de datos basicos (atomic)

+ *Integer* números enteros

	    1:5
    
+ *Numeric* números reales

    	pi
    
    	sqrt(2)

    ojo con los operadores logicos ver pag 45 de [Crawley](https://drive.google.com/file/d/0BzexxHVKtpiAaGJwMng5WTNveEk/view?usp=sharing)
    
+ *Logical* (TRUE - FALSE)

    	T
    
    	F
    
    	rep(T,10)

+ *Character* datos (cadenas) alfanuméricas


    	c("si","no","quien sabe")
    

  ver página 57 de [Bolker](https://drive.google.com/file/d/0BzexxHVKtpiAQjhBRDdZQW51WlU/view?usp=sharing) 

## Vectores

+ Un vector es un conjunto de datos básicos (atómicos o escalares). 

+ Una forma de crear un vector es usando la función concatenación:

		v <- c("Primero","Segundo","Tercero") 

+ Otras formas:

		b <- 1:10

 		n <- rep("La gallina turuleca",10)

 		m <- seq(1,3,by=0.2)

 	ver ?seq

## Functiones Vectoriales

+ Funciones que realizan operaciones sobre vectores

		sum(b)
		sum(m)
		sum(n)

		mean(b)

		max(b)

		length(b)

		summary(b)

	ver pag 63 de [Crawley](https://drive.google.com/file/d/0BzexxHVKtpiAaGJwMng5WTNveEk/view?usp=sharing)

+ Información sobre vectores

		class(b)

		str(b)

+ Operaciones sobre vectores


		v <- runif(100,1,10)

	ver ?runif

		v <- trunc(v)
		
		v == 10

		v <- v * pi

		v == pi

+ Extraer valores o subconjuntos

	See utiliza el operador []

		v[23]

		v[1:3]

	Puede utilzar un vector *logical* 
		
		v[T]
		v[c(T,F)]

		v[v==pi]

		v[v<pi]

## Ejercicio 2 

>1. Calcule vectores aleatorios utilizando distintas distribuciones de probabilidad, ver ?rpois ?rnorm ?rexp


>2. Calcule cuantos son mayores que la media, es la distribución simétrica?


+ Posible respuesta 

		v <- rnorm(1000,5,5)
		length(v[v>mean(v)])

		v <- rexp(1000,1/5)
		length(v[v>mean(v)])

		plot(v)
		plot(sort(v))
		plot(rev(sort(v)))
		hist(v)


## Listas

+ Las listas son colecciones de diferentes datos atómicos o vectores

		li <- list(elvector=v,numeros=b,gallinas=n)

		li

		li$gallinas

		li$gal

## Data.frames

+ Son listas con vectores de igual longitud: tablas de datos

		da <- data.frame(tiempo=1:100, nor=rnorm(100,5,5),exp=rexp(100,1/5),rpois(100,5))

		str(da)

		da$nor

		names(da)

		names(da)[5] <- "pois"

## Otros gráficos 

	install.packages("ggplot2")
	library(ggplot2)
	
	ggplot(da,aes(tiempo,nor)) + geom_point(size=1)
 
	ggplot(da,aes(tiempo,nor)) + geom_point(size=1) + theme_bw()

	g <-ggplot(da,aes(tiempo,nor)) + geom_point(size=1) + theme_bw()

	g + geom_point(aes(tiempo,exp))

	g + geom_point(aes(tiempo,exp),colour="red")

<http://www.noamross.net/blog/2012/10/5/ggplot-introduction.html>


## Tarea para el hogar

	+ Leer sobre Matrices y Factores en R de cualquiera de los libros de referencia


## Referencias

1. [Henry SM (2009) A Primer of Ecology with R. Springer.](https://drive.google.com/file/d/0BzexxHVKtpiAVlhfLWRiS2d4aWM/view?usp=sharing)

1. [Crawley MJ (2012) The R Book. 2nd Edition. Wiley. ](https://drive.google.com/file/d/0BzexxHVKtpiAaGJwMng5WTNveEk/view?usp=sharing)

1. [Bolker B (2008) Ecological Models and Data in R. Princeton University Press.](https://drive.google.com/file/d/0BzexxHVKtpiAQjhBRDdZQW51WlU/view?usp=sharing)