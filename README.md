### Prueba Técnica para LIS DATA SOLUTIONS
Este repositorio contiene la solución a la prueba técnica de Lis Data Solutions, que consiste en dos partes principales:

### Análisis de Datos con Python
En esta sección se aborda el análisis de los retrasos de los vuelos utilizando el lenguaje Python. El archivo 'DS_Prueba_tecnica.ipynb' contiene los enunciados de los ejercicios y las soluciones propuestas.
-Cálculo de los retrasos medios de salida y llegada.
-Análisis de los retrasos por aerolínea.
-Identificación del aeropuerto con más retrasos de salida.
-Visualización y conclusiones de los resultados.

### Modelado y ETL
Esta parte se centra en un problema de modelado e implementación de ETL utilizando Python.

### Diagrama del modelo de datos
Se ha diseñado un modelo dimensional que cubre los requisitos solicitados. El objetivo es proporcionar un sistema de BI que permita al responsable de compras tomar decisiones tanto en el análisis financiero de las compras, como en el análisis de proveedores. 
1. Proceso de negocio y granularidad
  La granularidad se centra en las compras realizadas. Cada transacción de compra es el evento más pequeño que se registra. A partir de ahí se extraen las diferentes métricas y dimensiones.
  La granularidad de los hechos sera a nivel de Factura. Cada compra realizada por un proveedor tiene su correspondiente detalle (fecha, importe, productos).
2. Dimensiones
   Dim_Date: fechas asociadas a la compra. Permite análisis por periodo y es esencial para calcular tiempo entre fecha de pedido y recepción.
   Dim_Supplier: información sobre proveedores. 
   Dim_Currencies: monedas utilizadas en las compras.
   Dim_Section: secciones empresa.
   Dim_Product: detalles productos comprados.
4. Hechos y Medidas
   Imprte de la compra: total gastado en cada compra, en euros.
   Número de productos: cantidad productos adquiridos de un proveedor.
   Lead Time Real: tiempo entre la fecha de pedido y la de recepción de los productos.
   Lead Time Teórico: valor constante en función del proveedor. 10 nacionales-20 europeos-45 no europeos.
6. Relaciones entre las tablas
Diseño para permitir consultas y análisis.
Fact_purchase: tabla de hechos que se conecta con las dimensiones Dim_Date, Dim_Supplier, Dim_Currencies, Dim_Section y Dim_Product.
Dim_Date: se conecta con Fact_Purchase mediante la fecha de la factura, fecha recepción y fecha pedido.
Dim_Supplier: se conecta con Fact_Purchase mediante proveedor asociado a cada compra. Se conecta también con Dim_Currency para determinar moneda.
Dim_Currencies: Relacionada con Fact_Purchase para convertir importes a euros.
Dim_Section:Relacionada con Fact_Purchase para categorizar compras según sección.
Dim_Product:Relacionada con Fact_Purchase_Product que tiene info sobre productos comprados en cada transacción.
8. Conclusiones
   -Granularidad: a nivel compra/factura para analizar cada transacción y comparar con proveedores y productos. Cada compra tiene una fecha asociada.
   -Dimensiones: proveedor, moneda, producto, sección y fecha. Son las áreas solicitadas.
   -Medidas: importe de compra y ranking de proveedores basado en cantidad de productos y lead tiempo real.
9. Diagrama. [DIAGRAMA%20DATAMART%20LISDATASOL.png] (https://github.com/mburgueno9/prueba_lisdata/blob/main/DIAGRAMA%20DATAMART%20LISDATASOL.png?raw=true)
