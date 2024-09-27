# CC216--TP-2024-2-
Análisis EDA: Hotel booking demand . La investigación presenta dos conjuntos de datos sobre la demanda de reservas hoteleras, uno correspondiente a un hotel de tipo resort (H1) y otro a un hotel urbano (H2) .


## 1. Introducción <a name="introduction"></a>

El artículo titulado "**Hotel Booking Demand Datasets**", escrito por Antonio Nuno de Almeida, Ana Nunes y Luis, aborda la importancia y la utilidad de los conjuntos de datos relacionados con la demanda de reservas hoteleras. Publicado el 2 de enero de 2019, este trabajo se enmarca dentro de un contexto multidisciplinario que combina aspectos de análisis de datos, gestión hotelera y técnicas de aprendizaje automático.

La investigación se centra en la recopilación y análisis de datos sobre reservas hoteleras, lo que permite a los investigadores y profesionales del sector comprender mejor los patrones de comportamiento de los consumidores. A través del uso de estos conjuntos de datos, se pueden desarrollar modelos predictivos que ayudan a anticipar la demanda, optimizar la gestión de ingresos y mejorar la experiencia del cliente. Este enfoque no solo beneficia a los hoteles en términos de eficiencia operativa, sino que también contribuye a una toma de decisiones más informada basada en datos concretos.

<img src="hotel_booking.jpg" alt="Reservas Hotel" style="width: 700px;"/>
<center>Figura 1: Reservas de Hotel</center>

<p></p>

En resumen, el trabajo destaca la relevancia de los datasets sobre demanda hotelera como herramientas clave para el análisis y la mejora continua en la industria del turismo.

## 2. Objetivos <a name="objectives"></a>

### Generales:
- Realizar un análisis exploratorio de un conjunto de datos (EDA), generando visualizaciones, preparando los datos y extrayendo conclusiones iniciales utilizando R/RStudio como herramienta de software.
- Explorar diferentes aspectos del comportamiento del consumidor en el sector hotelero.

### Específicos:
- Desarrollar modelos de predicción para clasificar la probabilidad de cancelación de una reserva hotelera.

## 3. Conjunto de Datos <a name="dataset"></a>

Se cuenta con un total de **119,390** datos y **32 variables** que provienen de la plataforma ScienceDirect, una fuente de bibliografía académica revisada por pares de Elsevier. El artículo describe dos conjuntos de datos de la demanda de hoteles: uno de un hotel resort ("**Resort Hotel**") y otro de un hotel urbano ("**City Hotel**"). Ambos conjuntos de datos comprenden reservas entre el 1 de julio de 2015 y el 31 de agosto de 2017.

<img src="datasets.jpg" alt="Datasets" style="width: 700px;"/>
<center>Figura 2: Datasets de Hoteles</center>

## 4. Caso de Análisis <a name="case_analysis"></a>

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

```R
# Objetivo: Realizar un análisis exploratorio del conjunto de datos
L <- readLines("hotel_booking_demand.csv", n = 1)
if (grepl(",", L)) print("File has an English format")
