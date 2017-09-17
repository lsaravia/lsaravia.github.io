---
comments: true
title: "Metapoblaciones - 4.1"
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

## Estimación de parámetros

+ Función de likelihood (verosimilitud) nos dice cual es la probabilidad de obtener una salida del modelo dado un conjunto de parámetros.

+ Si uno conoce o deriva la función de likelihood puede maximizarla para obtener los parámetros que mejor ajustan

+ En el caso de no conocer la función de likelihood hay un método que se llama Aproximate Bayesian Computation (ABC), que sirve para obtener estimaciones de los parámetros y sus intervalos de confianza.

+ Suponiendo que tenemos un conjunto de datos de campo/experimentales, el algorítmo para el método es el siguiente:

	1. Se elige un rango de valores posibles para cada parámetro
	2. Se toma un valor de los parámetros a partir de una distribución uniforme en ese rango
	3. Se corre el modelo
	3. Se comparan los datos con la salida del modelo, utilizando alguna medida de distancia, por ejemplo: suma de cuadrados de la diferencia entre observado y simulado, o el valor absoluto de esa diferencia.
	4. Si esta distancia no supera un valor límite arbitrario se guarda el conjunto de parámetros, sino se los descarta.
	5. Se vuelve al paso 2.

+ A medida que hacemos mayor cantidad de simulaciones más exacta va a ser la estimacion de la distribución de los parámetros. 

+ Para implementar esto en R necesitamos un conjunto de datos, vamos a usar datos simulados con el modelo espacialmente explicito:

```R     

# borramos todos las variables y funciones para empezar de cero 
#
rm(list())

source("Meta_fun.r")

datos <- sim_parches1(20,20,.5,100,.6,.3,0)

# elimino los primeros valores

datos <- datos[51:100]

```

+ Esa era la parte fácil ahora vamos a implementar la función, y estimamos los parámetros asumiendo el modelo con error de proceso, o el IBM:

```R     

estima_ABC <- function(dat,m,g,v,dlim,sim=1000)
{
# vamos a simular la longitud de los datos + 500 
    lendat <- length(dat)
	time <- 500+lendat
    da <- data.frame(matrix(, nrow = sim, ncol = 4))

    names(da) <- c("m","g","v","dis")  
    j <-1

	for(i in 1:sim){
		# calcula parametros
    ms <- runif(1,m[1],m[2])
		gs <- runif(1,g[1],g[2])
		vs <- runif(1,v[1],v[2])
    
    # Corre el modelo
		out <- levins_pro(time,ms,gs,trunc(vs))
    
    # selecciona la ultima parte
    out <- out[500:500+lendat]

		dis <- sum((dat-out)^2)
    if(dis <= dlim){
        da[j,]<-c(ms,gs,vs,dis)
        j <- j + 1
    }

	}
return(da)
}


```

+ Es recomendable guardar esto en Meta_fun.r y hacer una depuración verificando paso a paso lo que va haciendo la función.

    Un problema es que no tenemos idea de cual puede ser el valor de *dlim*, podemos hacer una primera corrida exploratoria, poniendo un valor muy grande de *dlim* y con .

```R     


source("Meta_fun.r")

set.seed(1)

prueba <- levins_pro(500,200,.6,.3,400)

prueba <- prueba[451:500]

fit <- estima_ABC(prueba,c(.59,.61),c(.29,.31),c(399,401),1e10)

```

+ Ahora podemos ver si funciona bien el método y el rango de variación de *dlim*

```R     

mean(fit$dis)
range(fit$dis)
hist(fit$dis)
fit[fit$dis==min(fit$dis),]

mean(fit$m)
sd(fit$m)
range(fit$m)
hist(fit$m)

mean(fit$g)
sd(fit$g)
range(fit$g)
hist(fit$g)

mean(fit$v)
sd(fit$v)
range(fit$v)
hist(fit$v)


```

+ Ahora falta hacerlo con el otro conjunto de datos

```R     

fit <- estima_ABC(datos,c(.4,.8),c(.1,.4),c(200,450),41000)

mean(fit$m)
sd(fit$m)
range(fit$m)
hist(fit$m)

mean(fit$g)
sd(fit$g)
range(fit$g)
hist(fit$g)

mean(fit$v)
sd(fit$v)
range(fit$v)
hist(fit$v)
```
    
    
## Referencias

1. Hartig F, Calabrese JM, Reineking B, Wiegand T, Huth A (2011) Statistical inference for stochastic simulation models – theory and application. Ecol Lett 14: 816–827. doi:10.1111/j.1461-0248.2011.01640.x.

1. Ross J V (2006) Stochastic models for mainland-island metapopulations in static and dynamic landscapes. Bull Math Biol 68: 417–449. doi:10.1007/s11538-005-9043-y. <
https://drive.google.com/file/d/0BzexxHVKtpiAWXNzaFFiMXNabk0/view?usp=sharing>

1. Renshaw E (1993) Modelling biological populations in space and time. Cambridge University Press.
Cap 7 <https://drive.google.com/file/d/0BzexxHVKtpiAYTNMNlQ2b2o2c1k/view?usp=sharing>

1. Black AJ, McKane AJ (2012) Stochastic formulation of ecological models and their applications. Trends Ecol Evol 27: 337–345. doi:10.1016/j.tree.2012.01.014.<https://drive.google.com/file/d/0BzexxHVKtpiAY05KZnJpMC10SWM/view?usp=sharing>

1. Henry SM (2009) A Primer of Ecology with R. Springer. <https://drive.google.com/file/d/0BzexxHVKtpiAVlhfLWRiS2d4aWM/view?usp=sharing>

1. Crawley MJ (2012) The R Book. 2nd Edition. Wiley. <https://drive.google.com/file/d/0BzexxHVKtpiAaGJwMng5WTNveEk/view?usp=sharing>

1. Bolker B (2008) Ecological Models and Data in R. Princeton University Press. <https://drive.google.com/file/d/0BzexxHVKtpiAQjhBRDdZQW51WlU/view?usp=sharing>