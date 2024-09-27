# CC216--TP-2024-2-
Análisis EDA: Hotel booking demand . La investigación presenta dos conjuntos de datos sobre la demanda de reservas hoteleras, uno correspondiente a un hotel de tipo resort (H1) y otro a un hotel urbano (H2) .

## Contenidos

1. [INTRODUCCIÓN](#data1)

2. [OBJETIVOS](#data2)

3. [CONJUNTO DE DATOS](#data3)
        
4. [CASO DE ANÁLISIS](#data4)
    
5. [DATASET](#data5)

6. [ANÁLISIS EXPLORATORIO DE DATOS](#data6)

7. [CONCLUSIONES](#data7)
   
8. [RECOMENDACIONES](#data8)
    
9. [CONCLUSIONES](#data9)

## 1. Introducción <a name="data1"></a>

<center><p style="text-align: justify;">
El artículo titulado "<strong>Hotel Booking Demand Datasets</strong>", escrito por Antonio Nuno de Almeida, Ana Nunes y Luis, aborda la importancia y la utilidad de los conjuntos de datos relacionados con la demanda de reservas hoteleras. Publicado el 2 de enero de 2019, 
este trabajo se enmarca dentro de un contexto multidisciplinario que combina aspectos de análisis de datos, gestión hotelera y técnicas de aprendizaje automático.</center></p>

<p style="text-align: justify;">
La investigación se centra en la recopilación y análisis de datos sobre reservas hoteleras, 
lo que permite a los investigadores y profesionales del sector comprender mejor los patrones de comportamiento de los consumidores. A través del uso de estos conjuntos de datos, se pueden desarrollar modelos predictivos que ayudan a anticipar la demanda, optimizar la gestión de ingresos y mejorar la experiencia del cliente. Este enfoque no solo beneficia a los hoteles en términos de eficiencia operativa, sino que también contribuye a una toma de decisiones más informada basada en datos concretos.
</p>

<img src="best-hotel-booking-form-wordpress-plugins.jpg" alt="Reservas Hotel" style="width: 700px;"/>
<center>Figura 1: Reservas de Hotel</center>

<p></p>

En resumen, el trabajo destaca la relevancia de los datasets sobre demanda hotelera como herramientas clave para el análisis y la mejora continua en la industria del turismo.

## 2. Objetivos <a name="data2"></a>

### Generales:
- Realizar un análisis exploratorio de un conjunto de datos (EDA), generando visualizaciones, preparando los datos y extrayendo conclusiones iniciales utilizando R/RStudio como herramienta de software.
- Explorar diferentes aspectos del comportamiento del consumidor en el sector hotelero.

### Específicos:
- Desarrollar modelos de predicción para clasificar la probabilidad de cancelación de una reserva hotelera.

## 3. Conjunto de Datos <a name="data3"></a>

Se cuenta con un total de **119,390** datos y **32 variables** que provienen de la plataforma ScienceDirect, una fuente de bibliografía académica revisada por pares de Elsevier. El artículo describe dos conjuntos de datos de la demanda de hoteles: uno de un hotel resort ("**Resort Hotel**") y otro de un hotel urbano ("**City Hotel**"). Ambos conjuntos de datos comprenden reservas entre el 1 de julio de 2015 y el 31 de agosto de 2017.

<img src="datasets.jpg" alt="Datasets" style="width: 700px;"/>
<center>Figura 2: Datasets de Hoteles</center>

## 4. Caso de Análisis <a name="data4"></a>

### Origen de los Datos:
- **Autores**: Antonio Nuno de Almeida, Ana Nunes y Luis.
- **Fecha de publicación**: 2 de enero de 2019.
- **Fuente**: ScienceDirect.
- **Instituto**: Instituto Universitario de Lisboa en Portugal.

### Credibilidad de los Datos:
Los datos provienen de consultas realizadas al sistema de gestión de propiedades (PMS) de los hoteles, almacenados en formato SQL de registros administrativos anteriores, lo que garantiza su confiabilidad.

### Casos de Uso Aplicables:
- **Cadenas hoteleras**: Optimización de cartera, mejora de la satisfacción del cliente, expansión de mercado.
- **Propietarios de hoteles independientes**: Oportunidades de nicho, diferenciación de servicios.
- **Investigadores académicos**: Estudios sobre el comportamiento del consumidor en el turismo y la gestión hotelera.
- **Organismos turísticos**: Comprensión del flujo turístico y desarrollo de políticas.

### Problemas o Necesidades que Responde el Análisis:

- **Mejorar la rentabilidad de los hoteles** mediante estrategias de precios dinámicos y promociones en temporadas bajas.
- **Mejorar la experiencia del cliente** con servicios personalizados para clientes recurrentes.
- **Optimizar la fluctuación de ingresos** con estrategias de marketing adecuadas a los periodos de menor actividad.


### Insights:

- La baja o la alta tasa de cancelaciones antes de tiempo podría significar un problema para el 
  negocio de los hoteles , algunas hipótesis podrían ser los cambios climáticos, las temporadas 
  altas de vacaciones, políticas de cancelaciones muy flexibles (factores que influyen en las 
  cancelaciones )

- El hotel debería implementar una estrategia de precios dinámica que tenga en cuenta tanto la 
  estacionalidad como el tipo de habitación, brindando descuentos o paquetes especiales en 
  temporadas altas a las habitaciones menos visitadas o invertir en aquellas con menos visitas.

- La estacionalidad está relacionado tanto por los tipos de habitación y por las temporadas , 
  asi que podriamos analizar y alzar los precios en las temporadas altas 

- Debido a la existencia de clientes nuevos y repetidos , se podría crear un servicio especial 
  para los clientes repetidos , accesos premium a eventos dentro del hotel, cupones o créditos 
  por visita y así poder aumentar la demanda de personas que visitan cada año.//(Por cada 100 
  personas cuántas son recurrentes)
  
Preguntas Clave para el Análisis <a name="questions"></a>

- ¿Cuántas reservas se realizan por tipo de hotel?
- ¿Está aumentando la demanda con el tiempo?
- ¿Cuáles son las temporadas de alta y baja demanda?
- ¿Cuántas reservas incluyen niños y/o bebés?
- ¿Es importante contar con espacios de estacionamiento?
- ¿En qué meses del año se producen más cancelaciones de reservas?

## 5. Dataset <a name="data5"></a>
Proporcionamos una tabla que describe las diferentes variables contenidas en el conjunto de datos y las define según su tipo y una breve descripción:

<table>
  <thead>
    <tr>
      <th>Variable</th>
      <th>Tipo</th>
      <th>Descripción</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>hotel</td>
      <td>Categórico</td>
      <td>Tipo de Hotel (Resort - City)</td>
    </tr>
    <tr>
      <td>is_canceled</td>
      <td>Numérico</td>
      <td>Indica si la reserva fue cancelada (1 Sí / 0 No)</td>
    </tr>
    <tr>
      <td>lead_time</td>
      <td>Numérico</td>
      <td>Días entre la reserva y la llegada</td>
    </tr>
    <tr>
      <td>arrival_date_year</td>
      <td>Numérico</td>
      <td>Año de la fecha de llegada</td>
    </tr>
    <tr>
      <td>arrival_date_month</td>
      <td>Categórico</td>
      <td>Mes de la fecha de llegada</td>
    </tr>
    <tr>
      <td>arrival_date_week_number</td>
      <td>Numérico</td>
      <td>Número de la semana del año de la llegada</td>
    </tr>
    <tr>
      <td>arrival_date_day_of_month</td>
      <td>Numérico</td>
      <td>Día del mes de la llegada</td>
    </tr>
    <tr>
      <td>stays_in_weekend_nights</td>
      <td>Numérico</td>
      <td>Número de noches de estancia en el fin de semana</td>
    </tr>
    <tr>
      <td>stays_in_week_nights</td>
      <td>Numérico</td>
      <td>Número de noches de estancia durante la semana</td>
    </tr>
    <tr>
      <td>adults</td>
      <td>Numérico</td>
      <td>Número de adultos incluidos en la reserva</td>
    </tr>
    <tr>
      <td>children</td>
      <td>Numérico</td>
      <td>Número de niños incluidos en la reserva</td>
    </tr>
    <tr>
      <td>babies</td>
      <td>Numérico</td>
      <td>Número de bebés incluidos en la reserva</td>
    </tr>
    <tr>
      <td>meal</td>
      <td>Categórico</td>
      <td>Tipo de comida reservado</td>
    </tr>
    <tr>
      <td>country</td>
      <td>Categórico</td>
      <td>País del cliente</td>
    </tr>
    <tr>
      <td>market_segment</td>
      <td>Categórico</td>
      <td>Segmento de mercado al que pertenece la reserva</td>
    </tr>
    <tr>
      <td>distribution_channel</td>
      <td>Categórico</td>
      <td>Canal de distribución de la reserva</td>
    </tr>
    <tr>
      <td>is_repeated_guest</td>
      <td>Numérico</td>
      <td>Indica si es un huésped recurrente</td>
    </tr>
    <tr>
      <td>previous_cancellations</td>
      <td>Numérico</td>
      <td>Número de reservas anteriores canceladas</td>
    </tr>
    <tr>
      <td>reserved_room_type</td>
      <td>Categórico</td>
      <td>Tipo de habitación reservada</td>
    </tr>
    <tr>
      <td>assigned_room_type</td>
      <td>Categórico</td>
      <td>Tipo de habitación asignada</td>
    </tr>
    <tr>
      <td>booking_changes</td>
      <td>Numérico</td>
      <td>Número de cambios en la reserva</td>
    </tr>
    <tr>
      <td>deposit_type</td>
      <td>Categórico</td>
      <td>Tipo de depósito (No Deposit, Non Refund, Refundable)</td>
    </tr>
    <tr>
      <td>agent</td>
      <td>Numérico</td>
      <td>ID del agente que gestionó la reserva</td>
    </tr>
    <tr>
      <td>company</td>
      <td>Numérico</td>
      <td>ID de la compañía que gestionó la reserva</td>
    </tr>
    <tr>
      <td>days_in_waiting_list</td>
      <td>Numérico</td>
      <td>Días en la lista de espera</td>
    </tr>
    <tr>
      <td>customer_type</td>
      <td>Categórico</td>
      <td>Tipo de cliente</td>
    </tr>
    <tr>
      <td>adr</td>
      <td>Numérico</td>
      <td>Tarifa Diaria Promedio</td>
    </tr>
    <tr>
      <td>required_car_parking_spaces</td>
      <td>Numérico</td>
      <td>Número de espacios de aparcamiento requeridos</td>
    </tr>
    <tr>
      <td>total_of_special_requests</td>
      <td>Numérico</td>
      <td>Número de solicitudes especiales</td>
    </tr>
    <tr>
      <td>reservation_status</td>
      <td>Categórico</td>
      <td>Estado de la reserva (Check-Out, Canceled, No-Show)</td>
    </tr>
    <tr>
      <td>reservation_status_date</td>
      <td>Fecha</td>
      <td>Fecha del estado de la reserva</td>
    </tr>
  </tbody>
</table>

## 6. Análisis exploratorio de datos <a name="data6"></a>

### Cargar Datos:
```R
setwd("C:/Users/Usuario/OneDrive - Universidad Peruana de Ciencias/DATA SCIENCE")

datahotel <- read.csv("hotel_bookings.csv",header=T,sep = ",")
```

### Inspeccionar  Datos: 

filas y columnas del dataset
dim(datahotel)
```R
dim(datahotel)
```
                    [1] 119390     32


lista de los nombres de las columnas 
```R
colnames(datahotel)
[1] "hotel"                         
 [2] "is_canceled"                   
 [3] "lead_time"                     
 [4] "arrival_date_year"             
 [5] "arrival_date_month"            
 [6] "arrival_date_week_number"      
 [7] "arrival_date_day_of_month"     
 [8] "stays_in_weekend_nights"       
 [9] "stays_in_week_nights"          
[10] "adults"                        
[11] "children"                      
[12] "babies"                        
[13] "meal"                          
[14] "country"                       
[15] "market_segment"                
[16] "distribution_channel"          
[17] "is_repeated_guest"             
[18] "previous_cancellations"        
[19] "previous_bookings_not_canceled"
[20] "reserved_room_type"            
[21] "assigned_room_type"            
[22] "booking_changes"               
[23] "deposit_type"                  
[24] "agent"                         
[25] "company"                       
[26] "days_in_waiting_list"          
[27] "customer_type"                 
[28] "adr"                           
[29] "required_car_parking_spaces"   
[30] "total_of_special_requests"     
[31] "reservation_status"            
[32] "reservation_status_date" 
```
                   

estructura general del conjunto de datos
```R
str(datahotel)
'data.frame':	119390 obs. of  32 variables:
 $ hotel                         : chr  "Resort Hotel" "Resort Hotel" "Resort Hotel" "Resort Hotel" ...
 $ is_canceled                   : int  0 0 0 0 0 0 0 0 1 1 ...
 $ lead_time                     : int  342 737 7 13 14 14 0 9 85 75 ...
 $ arrival_date_year             : int  2015 2015 2015 2015 2015 2015 2015 2015 2015 2015 ...
 $ arrival_date_month            : chr  "July" "July" "July" "July" ...
 $ arrival_date_week_number      : int  27 27 27 27 27 27 27 27 27 27 ...
 $ arrival_date_day_of_month     : int  1 1 1 1 1 1 1 1 1 1 ...
 $ stays_in_weekend_nights       : int  0 0 0 0 0 0 0 0 0 0 ...
 $ stays_in_week_nights          : int  0 0 1 1 2 2 2 2 3 3 ...
 $ adults                        : int  2 2 1 1 2 2 2 2 2 2 ...
 $ children                      : int  0 0 0 0 0 0 0 0 0 0 ...
 $ babies                        : int  0 0 0 0 0 0 0 0 0 0 ...
 $ meal                          : chr  "BB" "BB" "BB" "BB" ...
 $ country                       : chr  "PRT" "PRT" "GBR" "GBR" ...
 $ market_segment                : chr  "Direct" "Direct" "Direct" "Corporate" ...
 $ distribution_channel          : chr  "Direct" "Direct" "Direct" "Corporate" ...
 $ is_repeated_guest             : int  0 0 0 0 0 0 0 0 0 0 ...
 $ previous_cancellations        : int  0 0 0 0 0 0 0 0 0 0 ...
 $ previous_bookings_not_canceled: int  0 0 0 0 0 0 0 0 0 0 ...
 $ reserved_room_type            : chr  "C" "C" "A" "A" ...
 $ assigned_room_type            : chr  "C" "C" "C" "A" ...
 $ booking_changes               : int  3 4 0 0 0 0 0 0 0 0 ...
 $ deposit_type                  : chr  "No Deposit" "No Deposit" "No Deposit" "No Deposit" ...
 $ agent                         : chr  "NULL" "NULL" "NULL" "304" ...
 $ company                       : chr  "NULL" "NULL" "NULL" "NULL" ...
 $ days_in_waiting_list          : int  0 0 0 0 0 0 0 0 0 0 ...
 $ customer_type                 : chr  "Transient" "Transient" "Transient" "Transient" ...
 $ adr                           : num  0 0 75 75 98 ...
 $ required_car_parking_spaces   : int  0 0 0 0 0 0 0 0 0 0 ...
 $ total_of_special_requests     : int  0 0 0 0 1 1 0 1 1 0 ...
 $ reservation_status            : chr  "Check-Out" "Check-Out" "Check-Out" "Check-Out" ...
 $ reservation_status_date       : chr  "2015-07-01" "2015-07-01" "2015-07-02" "2015-07-02" ...
```

visualizar los primeros registros de datos
```R
head(datahotel)
         hotel is_canceled lead_time arrival_date_year
1 Resort Hotel           0       342              2015
2 Resort Hotel           0       737              2015
3 Resort Hotel           0         7              2015
4 Resort Hotel           0        13              2015
5 Resort Hotel           0        14              2015
6 Resort Hotel           0        14              2015
  arrival_date_month arrival_date_week_number
1               July                       27
2               July                       27
3               July                       27
4               July                       27
5               July                       27
6               July                       27
  arrival_date_day_of_month stays_in_weekend_nights
1                         1                       0
2                         1                       0
3                         1                       0
4                         1                       0
5                         1                       0
6                         1                       0
  stays_in_week_nights adults children babies meal country
1                    0      2        0      0   BB     PRT
2                    0      2        0      0   BB     PRT
3                    1      1        0      0   BB     GBR
4                    1      1        0      0   BB     GBR
5                    2      2        0      0   BB     GBR
6                    2      2        0      0   BB     GBR
  market_segment distribution_channel is_repeated_guest
1         Direct               Direct                 0
2         Direct               Direct                 0
3         Direct               Direct                 0
4      Corporate            Corporate                 0
5      Online TA                TA/TO                 0
6      Online TA                TA/TO                 0
  previous_cancellations previous_bookings_not_canceled
1                      0                              0
2                      0                              0
3                      0                              0
4                      0                              0
5                      0                              0
6                      0                              0
  reserved_room_type assigned_room_type booking_changes
1                  C                  C               3
2                  C                  C               4
3                  A                  C               0
4                  A                  A               0
5                  A                  A               0
6                  A                  A               0
  deposit_type agent company days_in_waiting_list
1   No Deposit  NULL    NULL                    0
2   No Deposit  NULL    NULL                    0
3   No Deposit  NULL    NULL                    0
4   No Deposit   304    NULL                    0
5   No Deposit   240    NULL                    0
6   No Deposit   240    NULL                    0
  customer_type adr required_car_parking_spaces
1     Transient   0                           0
2     Transient   0                           0
3     Transient  75                           0
4     Transient  75                           0
5     Transient  98                           0
6     Transient  98                           0
  total_of_special_requests reservation_status
1                         0          Check-Out
2                         0          Check-Out
3                         0          Check-Out
4                         0          Check-Out
5                         1          Check-Out
6                         1          Check-Out
  reservation_status_date
1              2015-07-01
2              2015-07-01
3              2015-07-02
4              2015-07-02
5              2015-07-03
6              2015-07-03
```

### Procesamiento de Datos:

Identificación de Datos Faltantes:Proceso para identificar valores NA en el conjunto de datos.
Identificar la cantidad de valores NA en cada columna

```R
colSums(is.na(hotel_data))
                         hotel                    is_canceled 
                             0                              0 
                     lead_time              arrival_date_year 
                             0                              0 
            arrival_date_month       arrival_date_week_number 
                             0                              0 
     arrival_date_day_of_month        stays_in_weekend_nights 
                             0                              0 
          stays_in_week_nights                         adults 
                             0                              0 
                      children                         babies 
                             4                              0 
                          meal                        country 
                             0                              0 
                market_segment           distribution_channel 
                             0                              0 
             is_repeated_guest         previous_cancellations 
                             0                              0 
previous_bookings_not_canceled             reserved_room_type 
                             0                              0 
            assigned_room_type                booking_changes 
                             0                              0 
                  deposit_type                          agent 
                             0                              0 
                       company           days_in_waiting_list 
                             0                              0 
                 customer_type                            adr 
                             0                              0 
   required_car_parking_spaces      total_of_special_requests 
                             0                              0 
            reservation_status        reservation_status_date 
                             0                              0
```
Tratamiento de Datos Faltantes:Técnica utilizada para eliminar o completar datos faltantes (p. ej., imputación, eliminación).

```R
#Creamos una dataset de ayuda “dataset_clean”
dataset_clean <- na.omit(hotel_data)
# Eliminar columnas con más de un 50% de valores NA
dataset_clean <- hotel_data[, colMeans(is.na(hotel_data)) < 0.5]
View(dataset_clean)

```
Identificación de Datos Atípicos (Outliers):Procedimiento para detectar valores atípicos, como diagramas de caja (boxplots).

```R
# Crear un boxplot para visualizar outliers
boxplot(dataset_clean$adr, main = "Diagrama de Caja - ADR")

# Identificar outliers usando el rango intercuartil (IQR)
Q1 <- quantile(dataset_clean$adr, 0.25, na.rm = TRUE)
Q3 <- quantile(dataset_clean$adr, 0.75, na.rm = TRUE)
IQR <- Q3 - Q1

# Definir límites
lower_bound <- Q1 - 1.5 * IQR
upper_bound <- Q3 + 1.5 * IQR
outliers <- dataset_clean$adr[dataset_clean$adr < lower_bound | dataset_clean$adr > upper_bound]

```
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
</head>
<body>
    <table>
        <thead>
            <tr>
                <th>Estadística</th>
                <th>Valor</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>IQR</td>
                <td>Named num 56.7</td>
            </tr>
            <tr>
                <td>lower_b</td>
                <td>Named num -15.8</td>
            </tr>
            <tr>
                <td>outliers</td>
                <td>num [1:3793] 225 21 ...</td>
            </tr>
            <tr>
                <td>Q1</td>
                <td>Named num 69.3</td>
            </tr>
            <tr>
                <td>Q3</td>
                <td>Named num 126</td>
            </tr>
            <tr>
                <td>upper_b</td>
                <td>Named num 211</td>
            </tr>
        </tbody>
    </table>
</body>
</html>

Tratamiento de Datos Atípicos:Técnica(s) para transformar o manejar los valores atípicos (p. ej., winsorización, eliminación de outliers).

```R
# Winsorización de datos para limitar outliers
install.packages("DescTools")
library(DescTools)

# Calcular los percentiles 5% y 95%
lower_bound <- quantile(dataset_clean$adr, 0.05, na.rm = TRUE)
upper_bound <- quantile(dataset_clean$adr, 0.95, na.rm = TRUE)

# Winsorizar manualmente reemplazando valores fuera de los límites
dataset_clean$adr[dataset_clean$adr < lower_bound] <- lower_bound
dataset_clean$adr[dataset_clean$adr > upper_bound] <- upper_bound
#Volvemos a ejecutar el BoxPlot
boxplot(dataset_clean$adr, main = "Diagrama de Caja - ADR")

```
### Visualizacion de datos 

#PREGUNTA 1
```R
hotel_count <- hotel_data %>%
  group_by(hotel) %>%
  summarise(count = n())

ggplot(hotel_count, aes(x = hotel, y = count, fill = hotel)) +
  geom_bar(stat = "identity") +
  labs(title = "Numeros de booking por tipo de hotel", x = "tipo de hotel", y = "Numeros de booking") +
  theme_minimal()
```
#PREGUNTA 2
```R
# Convertir el nombre del mes a número, si es necesario
hotel_data$arrival_date_month <- match(hotel_data$arrival_date_month, month.name)

# Crear la columna 'year_month' combinando año y mes
hotel_data$year_month <- make_date(hotel_data$arrival_date_year, hotel_data$arrival_date_month, 1)

# Verifica la creación de la columna year_month
head(hotel_data$year_month)

# Agrupar por year_month y contar el número de reservas
demand_over_time <- hotel_data %>%
  group_by(year_month) %>%
  summarise(count = n())

# Visualización: gráfico de línea de demanda a lo largo del tiempo
ggplot(demand_over_time, aes(x = year_month, y = count)) +
  geom_line(color = "blue") +
  labs(title = "Demanda de Reservas a lo Largo del Tiempo", x = "Fecha", y = "Número de Reservas") +
  theme_minimal()
```

#PREGUNTA 3
```R
seasonality <- hotel_data %>%
  group_by(arrival_date_month) %>%
  summarise(count = n()) %>%
  arrange(match(arrival_date_month, month.name))


ggplot(seasonality, aes(x = factor(arrival_date_month, levels = month.name), y = count, fill = count)) +
  geom_bar(stat = "identity") +
  labs(title = "Temporada de Reserva", x = "Mes", y = "Number of Bookings") +
  theme_minimal()
```

#PREGUNTA 4
```R
lowest_demand_month <- seasonality[which.min(seasonality$count), ]
lowest_demand_month
```

#PREGUNTA 5
```R
children_bookings <- hotel_data %>%
  filter(children > 0 | babies > 0)

nrow(children_bookings)

ggplot(children_bookings, aes(x = factor(children > 0, levels = c(TRUE, FALSE)), fill = babies > 0)) +
  geom_bar() +
  labs(title = "Bookings with Children and/or Babies", x = "Children Present", y = "Number of Bookings") +
  theme_minimal()
```

#PREGUNTA 6
```R
parking_spaces <- hotel_data %>%
  group_by(required_car_parking_spaces) %>%
  summarise(count = n())

ggplot(parking_spaces, aes(x = required_car_parking_spaces, y = count, fill = required_car_parking_spaces)) +
  geom_bar(stat = "identity") +
  labs(title = "Importance of Parking Spaces", x = "Number of Parking Spaces", y = "Number of Bookings") +
  theme_minimal()
```

#PREGUNTA 7
```R
hotel_data$arrival_date_month <- match(hotel_data$arrival_date_month, month.name)

hotel_data$year_month <- make_date(hotel_data$arrival_date_year, hotel_data$arrival_date_month, 1)

cancellations <- hotel_data %>%
  filter(is_canceled == 1) %>%
  group_by(year_month) %>%
  summarise(cancel_count = n())

ggplot(cancellations, aes(x = year_month, y = cancel_count)) +
  geom_bar(stat = "identity", fill = "red") +
  labs(title = "Cancelaciones Mensuales", x = "Mes", y = "Número de Cancelaciones") +
  theme_minimal()

```

## 7. Conclusiones <a name="data7"></a>
A partir de los datos de reservas por tipo de hotel, podemos concluir que los hoteles urbanos (City hotels) tienden a ser más populares que los resorts. Esto podría deberse a varios factores, como la ubicación céntrica,

Al analizar la demanda de reservas a lo largo del tiempo, observamos que existe un aumento constante en las reservas de ambos tipos de hoteles, especialmente en los meses de vacaciones y eventos especiales.

Las temporadas altas coinciden con los meses de vacaciones (junio, julio y agosto) y eventos festivos importantes, donde se observan mayores volúmenes de reservas. 

## 8. Recomendaciones <a name="data8"></a>

Implementar tarifas dinámicas ajustadas a la estacionalidad, la demanda y el tipo de habitación. Durante las temporadas bajas, ofrecer promociones y descuentos específicos podría incentivar las reservas, mientras que en temporadas altas

Revisar las políticas de cancelación, especialmente en meses donde se detecta un mayor índice de cancelaciones. 

Crear programas de fidelización para premiar a los clientes recurrentes, brindándoles beneficios exclusivos como descuentos, mejoras de habitación, acceso a eventos o servicios personalizados.

Implementar una estrategia de mejora continua en la atención al cliente, basada en el análisis de las solicitudes especiales. Esto ayudará a personalizar la experiencia de cada huésped, mejorando la satisfacción y la retención.


## 9. Bibliografia <a name="data9"></a>
Antonio, N., De Almeida, A., & Nunes, L. (2018). Hotel booking demand datasets. Data In Brief, 22, 41-49. https://doi.org/10.1016/j.dib.2018.11.126

Gabara, E. (2024, 18 julio). Lo que el rendimiento de las reservas de tu hotel puede decirte sobre los patrones de demanda. Cloudbeds. https://www.cloudbeds.com/es/articulos/patrones-demanda-hotelera/

Internacional, S. (2024, 23 junio). Investigación de mercado hotelero. Investigación Internacional SIS. https://www.sisinternational.com/es/pericia/industrias/investigacion-de-mercado-hotelero/
Antonio, N., De Almeida, A., & Nunes, L. (2018b). Hotel booking demand datasets. Data In Brief, 22, 41-49. https://doi.org/10.1016/j.dib.2018.11.126


Internacional, S. (2024b, junio 23). Investigación de mercado hotelero. Investigación Internacional SIS. https://www.sisinternational.com/es/pericia/industrias/investigacion-de-mercado-hotelero/








