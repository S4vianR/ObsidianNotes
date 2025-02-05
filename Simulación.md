
## Análisis y diagnóstico

### Definición de objetivos

Establecer qué se quiere lograr con la mejora de la gestión de inventarios (por ejemplo, reducir costos, mejorar la precisión de los inventarios, aumentar la satisfacción del cliente, etc.).

## Recolección de datos

Recopilar información relevante sobre el inventario actual, incluyendo:
- Niveles de stock actuales.
- Historial de ventas.
- Tiempos de reposición.
- Costos de mantenimiento y almacenamiento.
- Proveedores y tiempos de entrega.
## Análisis de procesos actuales

Evaluar los procesos existentes de gestión de inventarios:
- Identificar cómo se realiza el seguimiento del inventario.
- Revisar los métodos de reabastecimiento.
- Analizar la precisión de los registros de inventario.
- Identificar cuellos de botella y áreas de ineficiencia.
## Evaluación de herramientas y tecnología

Revisar las herramientas y sistemas actuales utilizados para la gestión de inventarios (software, hojas de cálculo, etc.).

Evaluar si hay tecnologías más avanzadas que podrían implementarse (como sistemas de gestión de inventarios, RFID, etc.).
## Identificación de problemas y oportunidades

Identificar los principales problemas en la gestión de inventarios, como:
- Exceso de stock o falta de productos.
- Alta rotación de inventario o productos obsoletos.
- Errores en el registro de inventario.

Buscar oportunidades de mejora, como la implementación de mejores prácticas o nuevas tecnologías.
## Análisis de costos

Evaluar los costos asociados con la gestión de inventarios, incluyendo costos de almacenamiento, costos de obsolescencia, y costos de pedidos.

Identificar áreas donde se pueden reducir costos sin afectar la calidad del servicio.

## Benchmarking (Análisis comparativo)

Comparar las prácticas de gestión de inventarios con las de empresas similares o líderes en la industria para identificar mejores prácticas y estándares de rendimiento.  
## Documentación

Documentar todos los hallazgos, problemas identificados y oportunidades de mejora en un informe que sirva como base para las siguientes fases de la metodología.
## Mapa mental

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXer6OVf_yjMipZaNAfNoflWiwEQfu8gjaHm9Gfik1jgycm0dVAhZd27BGPEOOr3k0sSHmesmNnqFKI4rjZbWdPYwVpdVrcZ7F7qzy-L6HFE1_TnS6g3KIyY0ozII0OyPjl8I9V_1g?key=3l5gEV6ZU_r6D-rX30ahh8pr)  

## Tabla de simulación

| Elemento de Simulación      | Descripción                                                                                               | Métricas a Evaluar                                                                              |
| --------------------------- | --------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| Niveles de Inventario       | Simular diferentes niveles de inventario para determinar el stock óptimo.                                 | Tasa de rotación de inventario, costos de almacenamiento, niveles de servicio al cliente.       |
| Tiempos de Reposición       | Variar los tiempos de entrega de los proveedores para evaluar su impacto.                                 | Tiempo de ciclo de pedido, nivel de stock de seguridad, tasa de faltantes.                      |
| Demanda del Cliente         | Simular fluctuaciones en la demanda para prever cambios en el inventario.                                 | Tasa de cumplimiento de pedidos, costos de falta de stock, niveles de satisfacción del cliente. |
| Costos de Almacenamiento    | Evaluar el impacto de diferentes estructuras de costos de almacenamiento.                                 | Costos totales de almacenamiento, rentabilidad por producto, costos de obsolescencia.           |
| Métodos de Reabastecimiento | Probar diferentes métodos de reabastecimiento (justo a tiempo, reabastecimiento periódico).               | Tiempos de entrega, niveles de inventario, costos de pedido.                                    |
| Políticas de Inventario     | Simular políticas de inventario como FIFO, LIFO y promedio ponderado.                                     | Precisión de inventario, costos de productos vendidos, márgenes de ganancia.                    |
| Proveedores                 | Evaluar el desempeño de diferentes proveedores en términos de tiempos de entrega y calidad.               | Tiempos de entrega, tasa de defectos, costos de adquisición.                                    |
| Espacio de Almacenamiento   | Simular el uso del espacio de almacenamiento y su impacto en la eficiencia.                               | Utilización del espacio, costos de almacenamiento, tiempos de acceso a productos.               |
| Tecnologías de Inventario   | Evaluar el impacto de la implementación de tecnologías como RFID o software de gestión de inventarios.    | Precisión de inventario, tiempos de conteo, costos operativos.                                  |
| Escenarios de Crisis        | Simular escenarios de crisis (pandemias, desastres naturales) para evaluar la resiliencia del inventario. | Tiempos de recuperación, costos adicionales, niveles de servicio al cliente.                    |

# Modelo Base Proyecto

## Modelo Base

### Proveedor

Esta es la base del proveedor donde el produce elementos a llevar al almacén general usando la transportadora que se tiene a disposición.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfbwNiLGjuhAdDP_zjmmLkAPTvSSo9BywguLWNo75aHrFI6oDLXT8EtCHRALE3GrvZu00P4Iaaf1VqDxcG6i6cLFLm7bH-qpLXFmwa7QWBCLPmoVSe6ik_xJgmtkp8E6kBzEiRHYg?key=hJ4d-_cpZwk1YJ3hQuijviXk)

### Almacén general

Este es el almacén general donde se debe hacer toda la gestión de inventario

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcBx_lim-zSE0YjHtsLRdNgYa--66obB3X-QPddTXcJ3xBUW1ypVtiZd0-TnZljZGupwzb8ImZcEfKJcOD7zI3iIwaSOGnDrzBKa2JpNIYLz2cVicJf6c3_ChDka_Gz2CtI1C_H1A?key=hJ4d-_cpZwk1YJ3hQuijviXk)

## Tiempos

| Nombre                        | Distribución | Tiempo                 |
| ----------------------------- | ------------ | ---------------------- |
| Fuente proveedor              | Uniforme     | Min: 1, max: 3 minutos |
| Operador proveedor - Carga    | Exponencial  | 5 segundos             |
| Operador proveedor - Descarga | Exponencial  | 5 segundos             |
| Camión proveedor - Carga      | Exponencial  | 30 segundos            |
| Camión proveedor - Descarga   | Exponencial  | 1 minuto               |
| Operador 1 Almacén - Carga    | Exponencial  | 5 segundos             |
| Operador 2 Almacén - Descarga | Exponencial  | 5 segundos             |
| Operador 2 Almacén - Carga    | Exponencial  | 5 segundos             |
| Operador 1 Almacén - Descarga | Exponencial  | 5 segundos             |

# Avance de proyecto 3

## Actualización del modelo

Lo que se ha actualizado es que se agregó un AGV Path para que el camión del proveedor siga un camino previamente establecido
### Proveedor

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXd_hsWLE7qsFC_AYzOAD7hbBCVMrWntwoHy4yqmawVsBKslJ_KmeSnx61Er0wTb80d9PANhzj1nATQHP2uyQuiI3CuEylg8GSo7Q-ZJDNScTMLba4CpKeu0zfTTl19ab-3yMibY?key=liNlbkMH6AYYB9G4t_JfOVaa)

### Almacén

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXcdZJWdqF7aonRb2DzN6ARxZlpvKxsb-wWqrqjT9WBeqZnFKAeD7DJ-QL4NOJyV78GvJa4xvmIeriItDRqlP0lna19ucHxQm8dJCAOUbY6Xq_c8Jn8Nfn6MgTWQZmYP9JqBQwtlkw?key=liNlbkMH6AYYB9G4t_JfOVaa)

## Paso 5: Verificación del modelo

Como se estableció en el avance pasado, los tiempos se han establecido de manera correcta

| Nombre                        | Distribución | Tiempo                 |
| ----------------------------- | ------------ | ---------------------- |
| Fuente proveedor              | Uniforme     | Min: 1, max: 3 minutos |
| Operador proveedor - Carga    | Exponencial  | 5 segundos             |
| Operador proveedor - Descarga | Exponencial  | 5 segundos             |
| Camión proveedor - Carga      | Exponencial  | 30 segundos            |
| Camión proveedor - Descarga   | Exponencial  | 1 minuto               |
| Operador 1 Almacén - Carga    | Exponencial  | 5 segundos             |
| Operador 2 Almacén - Descarga | Exponencial  | 5 segundos             |
| Operador 2 Almacén - Carga    | Exponencial  | 5 segundos             |
| Operador 1 Almacén - Descarga | Exponencial  | 5 segundos             |

#### Fuente

Así como en la tabla de tiempos se estableció un tiempo con una distribución estadística de mínimo 1 minuto y un máximo de 3 minutos.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXf3LG4Hkkpd-4NdXAwcglwxVS_PMME5eVwXFVW8myEEeYgEn-MWwPEkErNQ--oBv41ZMwH4xLHquYA5r0kEOOoUmPrg7z1Y4IGg-KQ2cEeNtx0p5CU-0pQ0EDSiudMlEAqYe1DJGw?key=liNlbkMH6AYYB9G4t_JfOVaa)
  
#### Operador proveedor

Se estableció el tiempo de carga y descarga a 5 segundos con la distribución estadística así como se especificó en la tabla.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeGMetYI3TNb1r27x5Lvjs0-ptO5NOFke6fiUQd2WkDey29mDwvIpIdQCUwAQMk7TegrNjacbTODgCPPAznzX8jE4QHmFKpIwGdTPGe05aLZhAceNoC9OEaX3VjqgvjLlmRa5sRgg?key=liNlbkMH6AYYB9G4t_JfOVaa)

#### Camión proveedor

Como se dijo en la tabla, para el tiempo de carga por objeto se estableció que fuesen 30 segundos y para el tiempo de descarga por objeto fue de 1 minuto, ambas con la distribución exponencial.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXe2qGsQ1X67p3DhY-DgNg2hc-IlTd5zntU_Mpi5y3O5AaiJ7mxQWidmU8eSqj1E_jwL6vKBtSL27FAQR8vo_aL16bBhTqKhn-5f1JReVdmnDrgrK_8eE7tT38pFjxEeBE1eeiGR?key=liNlbkMH6AYYB9G4t_JfOVaa)

#### Operadores almacén

A ambos operadores se les estableció un tiempo de carga y descarga de 5 segundos cada uno con la distribución exponencial.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfQ4gGS3hWjIDa6LasJoJZuuM6lj89L4J1q_rCV4k5NHPRwc4q8faOnWaXccAcIo3yrCr6SUA6XMlnC_hkjdzkQOXiF2zDyS7ebJpdUGiNsP3KRf3BUkAcXl8vIPR6BzCJ8lBpo6g?key=liNlbkMH6AYYB9G4t_JfOVaa)

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

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXd1wXPqpJ-XmYCCo1MCDiFRPg7TcFOYUSDIkKMeCbUuMPFGrXNZILh1lcKyCFHdzpsI2G9lNYc1Wdh7gKtMOnJhwN2ppXV1e81PuqZHtaB1IZ59X-c5fIGuHpBQIJUJqaYPzla4SA?key=liNlbkMH6AYYB9G4t_JfOVaa)

### Escenario 2

6 horas de turno, 35 artículos por viaje, 2 operadores
- El camión ha tenido una salida por hora de 23.33 productos.
- En cantidad total los almacenes tienen 140 productos.
- El Operador 1 ha estado inactivo durante el 83.48% del tiempo.
- El Operador 2 ha estado inactivo durante el 61.21% del tiempo.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXfnekBgEMyPWWcDanU0IhD8zTQgGHw77MAZ5wKsWlTaXwD2hn_ngR9aTArsae9lRdHWUJutOkWtOQzj32Z8gp8P1eExNVx708Ks-6q7NYca2yJMfTV-NSUFuPb83u1Ayw?key=liNlbkMH6AYYB9G4t_JfOVaa)

### Escenario 3

12 horas de turno, 70 artículos por viaje, 3 operadores
- El camión ha tenido una salida por hora de 27.13 productos.
- En cantidad total los almacenes tienen 651 productos.
- El Operador 1 ha estado inactivo durante el 80.53% del tiempo.
- El Operador 2 ha estado inactivo durante el 72.14% del tiempo.
- El Operador 3 ha estado inactivo durante el 79.27% del tiempo.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXeSFv5kQRYhWI6MqpoE0FXoq6VT-wJ-R4mNQHlVPvB_aZvQcbesInhH6CQu2rtfvbAktR7rIm2h7NxadNU5ejfM7jIcyJ7Ar4pJmgA_vchPCLqufywHXh-UiajIB9ZZNOF1Lg4TLg?key=liNlbkMH6AYYB9G4t_JfOVaa)

## Paso 7: Generación del modelo final
### Tiempos

| Nombre                        | Distribución | Tiempo                 |
| ----------------------------- | ------------ | ---------------------- |
| Fuente proveedor              | Uniforme     | Min: 1, max: 3 minutos |
| Operador proveedor - Carga    | Exponencial  | 5 segundos             |
| Operador proveedor - Descarga | Exponencial  | 5 segundos             |
| Camión proveedor - Carga      | Exponencial  | 30 segundos            |
| Camión proveedor - Descarga   | Exponencial  | 1 minuto               |
| Operadores Almacén - Carga    | Exponencial  | 5 segundos             |
| Operadores Almacén - Descarga | Exponencial  | 5 segundos             |

### Cantidades

| Nombre           | Capacidad                                                      |
| ---------------- | -------------------------------------------------------------- |
| Salida productos | Contenido Máximo: 120 productos, tamaño de lote: 120 productos |
| Camión proveedor | 60 productos                                                   |

### Escenario final

### Simulación de 7 días, 60 artículos por viaje, 3 operadores, 3 racks

- El camión ha tenido una salida por hora de 29.32 productos.
- En cantidad total los almacenes tienen 5160 productos.
- El Operador 1 ha estado inactivo durante el 78.89% del tiempo.
- El Operador 2 ha estado inactivo durante el 76.68% del tiempo.
- El Operador 3 ha estado inactivo durante el 88.31% del tiempo.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdvrWTJ61X1d6nbpAc8jKjpMaMSsIPnuu3wR-jTcSiAu8qwj07B8TgdPiUpri4en-j9kyXzFSPD2QVWsVbtfOkvXShIkK7oRcswb76qeBg9YXIdtrkdC7m1RnnfMjcAv_vpj30G?key=liNlbkMH6AYYB9G4t_JfOVaa)

### Análisis de resultados
#### Eficiencia de Operadores

La alta tasa de inactividad de los operadores indica que puede haber cuellos de botella en el proceso de carga y descarga, o que los tiempos de operación no están optimizados. Esto sugiere la necesidad de revisar los procesos y posiblemente ajustar los tiempos de operación o el número de operadores.
#### Gestión de Inventarios

Con un total de 5160 productos en los almacenes, es esencial evaluar si esta cantidad es adecuada para cumplir con la demanda y los tiempos de reposición establecidos. Esto ayudará a determinar si se requiere un ajuste en las políticas de inventario.
#### Frecuencia de Salida

La salida de 29.32 productos por hora debe ser comparada con la demanda esperada para asegurar que el sistema pueda satisfacer las necesidades del cliente sin generar excesos de inventario.