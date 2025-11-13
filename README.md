# power_bi_sales_variedades_enterprise

🛍️ Variedades Enterprise – Dashboard de Ventas Power BI

📊 Descripción del Proyecto

Este proyecto presenta un dashboard interactivo en Power BI desarrollado para Variedades Enterprise, una empresa dedicada a la venta minorista.
El objetivo fue transformar los datos de ventas en insights accionables, optimizando la toma de decisiones a través de una interfaz clara, moderna y orientada a KPIs.


🚀 Principales Resultados

| Indicador                         | Resultado               |
| --------------------------------- | ----------------------- |
| 💰 **Ventas totales**             | $2,52 mil M             |
| 🏙️ **Ciudades líderes**          | Medellín y Barranquilla |
| 📈 **Crecimiento máximo mensual** | 329,22%                 |
| 🛒 **Categoría más rentable**     | Man_C56 (1,29 mil M)    |


🧠 Arquitectura del Modelo de Datos

El modelo relacional se construyó bajo principios Star Schema, conectando las tablas principales:
Ventas: contiene la transacción con medidas DAX personalizadas.
Productos: define la categoría, ID y precio de cada artículo.
Tiendas y Ciudades: permiten segmentación geográfica.
Medidas: agrupa cálculos DAX reutilizables como Total Ventas, Ventas Promedio y Crecimiento de Ventas.


⚙️ Medidas DAX Clave

Crecimiento de Ventas =
IF(
    ISFILTERED('Ventas'[Fecha]),
    ERROR("La medida rápida de inteligencia de tiempo solo se puede agrupar o filtrar mediante la jerarquía de datos proporcionada por Power BI."),
    VAR __PREV_MONTH = CALCULATE([Total Ventas], DATEADD('Ventas'[Fecha].[Date], -1, MONTH))
    RETURN
    DIVIDE([Total Ventas] - __PREV_MONTH, __PREV_MONTH)
)

🌍 Visualización Interactiva

🔗 Explora el Dashboard en Power BI (Acceso Microsoft)
https://app.powerbi.com/groups/me/reports/6482d798-7613-4fc7-90b1-66eb200a7a79?ctid=693cbea0-4ef9-4254-8977-76e05cb5f556&pbi_source=linkShare

🧩 Tecnologías Utilizadas

Power BI Desktop
DAX (Data Analysis Expressions)
Modelo Estrella (Star Schema)
Microsoft Excel / CSV
Mapas de Visualización y Filtros Dinámicos


📢 Créditos

Autor: Francisco Javier Rivera Rozo
Rol: Analista de Datos | BI Developer
Contacto: [LinkedInhttps://www.linkedin.com/in/franciscojavierriverarozo/](https://www.linkedin.com/in/franciscojavierriverarozo/)

🪪 Licencia
Este proyecto se distribuye bajo la licencia MIT. Puedes reutilizarlo y adaptarlo con atribución.
