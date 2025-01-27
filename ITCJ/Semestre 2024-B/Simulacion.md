

# Avance de proyecto 3

## Actualización del modelo

Lo que se ha actualizado es que se agregó un AGV Path para que el camión del proveedor siga un camino previamente establecido

  

### Proveedor

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdZ23Jdj9nsLYgalyWEwzG0zz0dX5qzhr-tKJAK4JKAyVr-bHWGvsJCrpN7gcPj2rxV_X4VorHfOXjuMeTyiTJieezGaE3ekkz87I1aA570XHKmtC63x1sQ5BbXb-3UC2VPAnHg?key=liNlbkMH6AYYB9G4t_JfOVaa)

  

### Almacén

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXclfYPvJI8WNtTkTEVkLunp4MEoBzgYwDxFo01feaTnNw7U3lKfwCr10wjep6MypivXTew1KhaBVz8mGH2XT7K4eSXPmml_5JBWFi1hixCXx_7GTK8ro28326vu0PO6BwAP14AkSg?key=liNlbkMH6AYYB9G4t_JfOVaa)

  
  
  
  
  
  
  

## Paso 5: Verificación del modelo

Como se estableció en el avance pasado, los tiempos se han establecido de manera correcta

|   |   |   |
|---|---|---|
|Nombre|Distribución|Tiempo|
|Fuente proveedor|Uniforme|Min: 1, max: 3 minutos|
|Operador proveedor - Carga|Exponencial|5 segundos|
|Operador proveedor - Descarga|Exponencial|5 segundos|
|Camión proveedor - Carga|Exponencial|30 segundos|
|Camión proveedor - Descarga|Exponencial|1 minuto|
|Operador 1 Almacén - Carga|Exponencial|5 segundos|
|Operador 2 Almacén - Descarga|Exponencial|5 segundos|
|Operador 2 Almacén - Carga|Exponencial|5 segundos|
|Operador 1 Almacén - Descarga|Exponencial|5 segundos|

  
  
  
  
  
  
  
  
  
  
  
  
  
  
  

#### Fuente

Así como en la tabla de tiempos se estableció un tiempo con una distribución estadística de mínimo 1 minuto y un máximo de 3 minutos.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdG5xEdAKDby-MuWaF_CvFMwXB8pcLhioOY6uZ9ZzJJw-RuaFzyCekeUNf5eqzVYmeFWjuog4Hova08VgfUouJpHLv82C0ujEy0iml-fWvpqvqYWH3da6X_erVEFb56MqZQjZ1nyA?key=liNlbkMH6AYYB9G4t_JfOVaa)

  

#### Operador proveedor

Se estableció el tiempo de carga y descarga a 5 segundos con la distribución estadística así como se especificó en la tabla.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXci436BZSiEYdLIBDAwll4PGM3jKOY9eFFIwpoT8gYUe3A283wjCFA9W-mWAp3DRKiefcMaYBkCnzximSWKUGu3gHr-2yOmg4VRiK_ciViGH5pGR6ZprH07R4PA1Co6zW6RwQPEKQ?key=liNlbkMH6AYYB9G4t_JfOVaa)

  
  

#### Camión proveedor

Como se dijo en la tabla, para el tiempo de carga por objeto se estableció que fuesen 30 segundos y para el tiempo de descarga por objeto fue de 1 minuto, ambas con la distribución exponencial.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcjzRyD68m_UE-r3INP2Le23j4_mhWJd2Kg_GPnXuc6J8p_13xPbGBphN1fykxu4LXgYBpt8KOuhGyzyT4DWJmni4i7yrbJGxtAxOSIhccN6B394e_LEXZ2O6RbJUWwVUMnez33?key=liNlbkMH6AYYB9G4t_JfOVaa)

  

#### Operadores almacén

A ambos operadores se les estableció un tiempo de carga y descarga de 5 segundos cada uno con la distribución exponencial.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdvW1ljGn2e4inAH8d6CRvg29d4Gf2pJZRgVAtdEBXV9Zmr7S-8un8g7rXDn6wXWXPU0mV24l0U4USQlDSnBAz79xbEptdsDnLh5YGPh-tJTbjiJ38TowKnHs9RItjSSg2iRwmPLQ?key=liNlbkMH6AYYB9G4t_JfOVaa)

  
  
  
  
  
  
  
  

## Paso 6: Validación del modelo

  

Se tomarán en cuenta los siguientes escenarios:

1. Turno de 8 hrs con el camión teniendo una capacidad de 60 artículos por viaje y tres operadores en el almacén.
    
2. Turno de 6 hrs con el camión teniendo una capacidad de 35 artículos por viaje y dos operadores en el almacén.
    
3. Turno de 12 hrs con el camión teniendo una capacidad de 70 artículos por viaje y tres operadores en el almacén.
    

### Escenario 1

8 horas de turno, 60 artículos por viaje, 3 operadores

- El camión ha tenido una salida por hora de 22.50 productos.
    
- En cantidad total los almacenes tienen 180 productos.
    
- El Operador 1 ha estado inactivo durante el 84.02% del tiempo.
    
- El Operador 2 ha estado inactivo durante el 76.29% del tiempo.
    
- El Operador 3 ha estado inactivo durante el 87.74% del tiempo.
    

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeJxkuCPFMp1NUpa-hVfzUQpsz3hW-zYFabqI8nE6IzecMfKpP659JsaeQUysWF8PRBgF1_65cjCQ3ZCVoX0ZVbTdi43YRh_tzQnvO-Nu266XIMxKdPNM7p2sqLsD9Vzgjomiz6sw?key=liNlbkMH6AYYB9G4t_JfOVaa)

### Escenario 2

6 horas de turno, 35 artículos por viaje, 2 operadores

- El camión ha tenido una salida por hora de 23.33 productos.
    
- En cantidad total los almacenes tienen 140 productos.
    
- El Operador 1 ha estado inactivo durante el 83.48% del tiempo.
    
- El Operador 2 ha estado inactivo durante el 61.21% del tiempo.
    

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdkbWPWYsCVeengrCI-IQCXgE04J4AqGq94WdLLFxxbmR2opvTj1HJEetb6Ux-XaNID5Kra-hwQ-j8jhCHbgnhfEnsM8gQxP_yWgJzsDYX-PpNsNp-VbkXSv8OjAtEkCw?key=liNlbkMH6AYYB9G4t_JfOVaa)

  
  
  
  
  
  
  
  
  
  

### Escenario 3

12 horas de turno, 70 artículos por viaje, 3 operadores

- El camión ha tenido una salida por hora de 27.13 productos.
    
- En cantidad total los almacenes tienen 651 productos.
    
- El Operador 1 ha estado inactivo durante el 80.53% del tiempo.
    
- El Operador 2 ha estado inactivo durante el 72.14% del tiempo.
    
- El Operador 3 ha estado inactivo durante el 79.27% del tiempo.
    

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXco0ZhTZtkBqZkkNN7LEoZpeEHAoI0Xr9A1oYDwHryTJB8deBIfPTjJ4VELbqVhICGg-6-q7K46CGH4nycbwVWc5Ruf9ZCNh_xQGAISueb2lQMtekemXHyMcRrI7Vdl0aRheB-tIg?key=liNlbkMH6AYYB9G4t_JfOVaa)

  
  
  
  
  
  
  
  
  
  

## Paso 7: Generación del modelo final

  

### Tiempos

  

|   |   |   |
|---|---|---|
|Nombre|Distribución|Tiempo|
|Fuente proveedor|Uniforme|Min: 1, max: 3 minutos|
|Operador proveedor - Carga|Exponencial|5 segundos|
|Operador proveedor - Descarga|Exponencial|5 segundos|
|Camión proveedor - Carga|Exponencial|30 segundos|
|Camión proveedor - Descarga|Exponencial|1 minuto|
|Operadores Almacén - Carga|Exponencial|5 segundos|
|Operadores Almacén - Descarga|Exponencial|5 segundos|

  

### Cantidades

  

|   |   |
|---|---|
|Nombre|Capacidad|
|Salida productos|Contenido Máximo: 120 productos, tamaño de lote: 120 productos|
|Camión proveedor|60 productos|

  
  
  
  
  
  
  
  
  
  

### Escenario final

### Simulación de 7 días, 60 artículos por viaje, 3 operadores, 3 racks

- El camión ha tenido una salida por hora de 29.32 productos.
    
- En cantidad total los almacenes tienen 5160 productos.
    
- El Operador 1 ha estado inactivo durante el 78.89% del tiempo.
    
- El Operador 2 ha estado inactivo durante el 76.68% del tiempo.
    
- El Operador 3 ha estado inactivo durante el 88.31% del tiempo.
    

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXch0So5QK-6XDGsoaeYGEdke-nfNfsGI8KFEL4vCTMnlfDYcqmny514FfXFHenWODBSoGOw8wZ_l1wU6PJtaqVlvzhel3jxysmn1nlaTgDgFYv_5euVlk071nfpG0dIRpcMDSzb?key=liNlbkMH6AYYB9G4t_JfOVaa)

  
  
  
  
  
  
  
  
  

### Análisis de resultados

  

#### Eficiencia de Operadores

La alta tasa de inactividad de los operadores indica que puede haber cuellos de botella en el proceso de carga y descarga, o que los tiempos de operación no están optimizados. Esto sugiere la necesidad de revisar los procesos y posiblemente ajustar los tiempos de operación o el número de operadores.

  

#### Gestión de Inventarios

Con un total de 5160 productos en los almacenes, es esencial evaluar si esta cantidad es adecuada para cumplir con la demanda y los tiempos de reposición establecidos. Esto ayudará a determinar si se requiere un ajuste en las políticas de inventario.

  

#### Frecuencia de Salida

La salida de 29.32 productos por hora debe ser comparada con la demanda esperada para asegurar que el sistema pueda satisfacer las necesidades del cliente sin generar excesos de inventario.

  

## Conclusiones

El modelo final ha sido configurado para simular el comportamiento del sistema de gestión de inventarios durante un período de 7 días. Los resultados obtenidos proporcionan una visión clara de la eficiencia operativa y las áreas que requieren atención. Se recomienda realizar un análisis más profundo para identificar las causas de la inactividad de los operadores y ajustar los procesos de gestión de inventarios para mejorar la eficiencia y satisfacción del cliente.

**