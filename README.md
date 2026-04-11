# Análisis de un test A/B para una tienda online
## Objetivo
Priorizar hipótesis de optimización del sitio web usando RICE e ICE y analizar una prueba A/B para evaluar si los cambios implementados generan un impacto positivo en los ingresos.
## Herramientas utilizadas
**Python (Pandas, Numpy, Scipy, Matplotlib) | Prueba Z | Prueba Mann Whitney | A/B testing**
## Análisis exploratorio de datos (EDA)
En esta etapa verifiqué que no hubiera datos ausentes o duplicados. Cabe señalar que en el dataset orders, encontré 58 visitantes que aparecían tanto en el grupo A como en el B, por lo que opté por eliminarlos ya que no había de saber a qué grupo pertenecían. 
## Priorización de hipótesis
Prioricé 9 hipóyesis de optimización del sitio web usando los *framewors* ICE y RICE. Al ordenarlas de forma descendente y comparar sus resultados en ambos *frameworks*, la hipótesis de agregar un formulario de suscripción a todas las páginas principales para compilar una lista de emails ocupó el tercer lugar de ICE con 11.20, pues su impacto fue de 7; su confianza, de 8 y su esfuerzo de 5. En RICE, se encontró en el primer puesto, ya que su alcance fue de 10 usuarios, el más alto. Concluí que esta era la opción más conveniente pues su impacto y confianza son relativamente altos, implica un esfuerzo medio y alcanza a la mayor cantidad de usuarios.
## Análisis del test A/B
Se realizaron gráficos para comparar el ingreso acumulado, el tamaño de pedido promedio acumulado, la diferencia relativa en el tamaño de pedido promedio acumulado y la tasa de conversión diaria por grupo a lo largo de la prueba. 

En el gráfico del ingreso acumulado, se observó un aumento significativo en los ingresos a partir del 8/19 hasta el final de la prueba por parte del grupo B.

<img width="988" height="490" alt="output" src="https://github.com/user-attachments/assets/ec263ee4-ba7a-4d47-8b5a-a36a4b1ccdb0" />

También, se identificaron *outliers* en el número de pedidos por usuario y precio de pedidos mediante el percentil 99 y gráficos de dispersión, considerando como anormales a los pedidos de más de $830.3 y a los usuarios que hicieron más de 2 pedidos.

<img width="700" height="470" alt="image" src="https://github.com/user-attachments/assets/79a0319f-43e7-4170-b647-23c8c095681b" />

<img width="713" height="470" alt="image" src="https://github.com/user-attachments/assets/328b6f33-fd46-40f4-bedb-f0025ceab52c" />

Finalmente, se realizaron las pruebas estadísticas. Por un lado, la prueba Z para determinar la significancia estadística de la diferencia de la conversión entre los grupos, tanto con los datos en bruto como con los datos filtrados (excluyendo los *outliers*), reveló que sí existía una diferencia significativa y que el grupo B tenía una mejor tasa de conversión que el A. Por otro lado, la prueba Mann-Whitney, tanto con los datos sin procesar y los filtrados, determinó que no había una diferencia significativa en el tamaño promedio de compra.

## Conclusiones
Según las pruebas estadísticas, el grupo B se convirtieron más usuarios en clientes en comparación con los del grupo A. Sin embargo, estos clientes no hicieron pedidos grandes, por lo que el tamaño promedio de compra no aumentó.

La prueba debería pararse ya que el grupo B fue el líder respecto a la tasa de conversión. Aunque el tamaño promedio no mejoró, el gráfico de ingresos acumulados por grupo muestra que estos fueron mucho mayores en los últimos días para el grupo B que para el A, lo cual es una evidencia más de que el cambio en la plataforma tuvo un impacto positivo en los ingresos. 
