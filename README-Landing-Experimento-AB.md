# Experimento A/B en una landing page

Proyecto guiado del programa de Análisis de Datos de TripleTen (Sprint 9). El caso, el dataset y los pasos vienen del curso. El análisis, la interpretación y las recomendaciones son míos.

## De qué trata

Se probaron dos versiones de una página de inicio (A y B) y hay que decidir cuál conviene dejar. El análisis compara las dos páginas en gasto promedio y en tasa de conversión, y revisa si la fuente de tráfico y el tipo de usuario se relacionan con la conversión.

## Datos

`landing_experiment.csv`: 40,000 usuarios expuestos a una de las dos versiones durante enero de 2026 (19,982 en A y 20,018 en B). Incluye región, dispositivo, fuente de tráfico, tipo de usuario, si convirtió y cuánto gastó. No tiene valores ausentes.

## Cómo lo trabajé

1. Validé los datos: usuarios, rango de fechas, gasto y categorías.
2. Comparé el gasto promedio de los usuarios convertidos con una prueba t de Welch.
3. Comparé la tasa de conversión con una prueba z de dos proporciones.
4. Probé la relación de la fuente de tráfico y del tipo de usuario con la conversión usando chi-cuadrada de independencia.
5. Visualicé conteos y proporciones de conversión por categoría para reforzar las pruebas.
6. Resumí los hallazgos y las recomendaciones para negocio.

## Resultados

| Indicador | Página A | Página B | Resultado |
|---|---|---|---|
| Tasa de conversión | 12.57 % | 15.96 % | Diferencia significativa (+3.39 puntos, p < 0.001) |
| Gasto promedio por usuario convertido | 61.09 | 68.75 | Diferencia significativa (p < 0.001) |

- Fuente de tráfico: hay asociación significativa con la conversión (p = 0.0341). Email convierte 14.99 %, Ads 14.74 %, Referral 13.88 % y Organic 13.79 %. Las diferencias son pequeñas; Organic aporta más conversiones en volumen pero es el canal menos eficiente.
- Tipo de usuario: no hay asociación significativa (p = 0.4736). Nuevos 14.36 % y recurrentes 14.09 %.

Recomendación: adoptar la página B, priorizar Email y Ads en adquisición, evaluar los canales por tasa y no solo por volumen, y no diferenciar la estrategia solo por usuario nuevo o recurrente.

## Alcance

El gasto se compara solo entre usuarios que convirtieron. Para la prueba de gasto usé la variante de Welch, que no asume varianzas iguales; no incluí una prueba de varianzas previa.

## Herramientas

Python, pandas, NumPy, Matplotlib, Seaborn, SciPy y statsmodels, en Jupyter Notebook.

## Cómo ejecutarlo

Abre `Proyecto-Landing-Experimento-AB.ipynb` en Jupyter o Google Colab. El dataset lo proporciona el curso y el notebook lo lee desde `/datasets/landing_experiment.csv`; si lo corres fuera de la plataforma, ajusta esa ruta.

## Autor

Cuauhtli Iancuic Galindo Alcantara
