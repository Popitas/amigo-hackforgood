# GRAFICOS CONTROL PAQUETE qcr

install.packages("qcr")
library("qcr")
library("qcc")

# Lectura de datos para el ejemplo
basedatos3 <- read.csv("C:/Users/Desiree/Desktop/HackforGood/basedatos3.csv", sep=";")

dim("basedatos3") 
str(basedatos3)

# Tabla de frecuencias para conocer el tamaÃ±o de las muestras
table(basedatos3$HOMBRES)


# Primero chequeo la normalidad de la variable a analizar
mean(basedatos3$HOMBRES)
sd(basedatos3$HOMBRES)

hist(basedatos3$HOMBRES,nclass=10,prob=T,xlab="Apertura de la población masculina",main="Histograma sobre la apertura de la población masculina")
lines(density(basedatos3$HOMBRES))

boxplot(basedatos3$HOMBRES, main="Tamaño de la apertura de la población masculina")
qqnorm(basedatos3$HOMBRES, main="Test de normalidad Q-Q plot")
qqline(basedatos3$HOMBRES)

# Creo lo objetos qcd (Quality Control Data) qcs.xbar (Quality Control Statistics)
# del tipo xbar

# GRAFICOS X-R
basedatos3s.qcd<-qcd(basedatos3)
media<-qcs.xbar(basedatos3s.qcd, std.dev="UWAVE-R")
# por defecto srd.dev="UWAVE-R" para graficos Media y R
summary(media)
plot(media, title="Valores de riesgo situados fuera del intervalo de seguridad (Oxígeno en sangre)")
