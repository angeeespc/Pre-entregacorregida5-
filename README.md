# 🛒 RetailPro — Sistema de Análisis de Datos y E-Commerce

Bienvenido al repositorio oficial de **RetailPro**, un proyecto integral de análisis de datos desarrollado para optimizar la estrategia comercial, la gestión de inventarios y el rendimiento operativo de un e-commerce del sector tecnológico (`Ventas_Tech_DB`).

---

## 📋 Descripción General del Proyecto

RetailPro nace con el propósito de resolver problemas críticos de negocio —como la identificación de fluctuaciones en ventas, el análisis de rendimiento por canales de venta (Online vs. Presencial) y el comportamiento de compra de los clientes— mediante la estructuración de bases de datos relacionales normalizadas (3NF), pipelines de datos en Power Query, modelado dimensional y consultas SQL avanzadas.

---

## 🛠️ Tecnologías y Herramientas Utilizadas

* **Gestión de Base de Datos / SQL:** Scripts relacionales para la creación, inserción y consultas avanzadas con motores compatibles (PostgreSQL / MySQL / SQL estándar).
* **ETL y Transformación:** Power Query para la limpieza, tipado, desduplicación y normalización de datos.
* **Modelado y Business Intelligence:** Power BI Desktop para el modelado dimensional (esquema en estrella), creación de tablas de fechas calculadas y medidas DAX avanzadas.
* **Control de Versiones:** Git y GitHub para la documentación y despliegue del código fuente.

---

## 🗂️ Estructura del Repositorio

El proyecto se encuentra organizado de forma modular según las etapas de desarrollo y pre-entregas del curso:

1. **`Pre-entrega 3.sql`** — Definición del esquema relacional base (`DROP TABLES`, `CREATE TABLES` para `categorias`, `clientes`, `productos`, `ventas` e inserción de datos de prueba)[cite: 2].
2. **`Pre-entrega 4.sql`** — Consultas SQL de negocio para extracción de métricas, resúmenes ejecutivos mensuales, ranking de productos y análisis condicionales[cite: 3].
3. **`Pre-entrega 5.sql`** — Consultas avanzadas utilizando `INNER JOIN`, `LEFT JOIN` (clientes/productos sin ventas) y `UNION ALL` para consolidados por canal de venta[cite: 4].
4. **`Apellido_Nombre_Checkpoint2.pbix`** — Archivo maestro de Power BI que incluye el modelo dimensional, la tabla de calendario y las medidas DAX clave[cite: 13].

---

## ⚙️ Instrucciones de Ejecución y Despliegue

Para levantar y ejecutar la base de datos de manera local y evitar errores de dependencias de llaves foráneas (`foreign keys`), sigue estrictamente el siguiente orden secuencial de los scripts SQL:

1. **Paso 1 (Estructura y Carga):** Ejecuta el script **`Pre-entrega 3.sql`** para limpiar bases de datos previas, crear las tablas maestras y transaccionales, e insertar los registros iniciales[cite: 2].
2. **Paso 2 (Métricas de Negocio):** Ejecuta **`Pre-entrega 4.sql`** para correr los reportes de resumen ejecutivo y ranking de productos[cite: 3].
3. **Paso 3 (Análisis Relacional):** Ejecuta **`Pre-entrega 5.sql`** para verificar las consultas con `JOINs` y consolidación por canales de venta[cite: 4].

---

## 📊 Modelado en Power BI y Medidas DAX Principales

El modelo implementa un **esquema en estrella** conectando tablas de dimensiones (`Dim_Clientes`, `Dim_Productos`, `Dim_Categorias`, `Dim_Fechas`) con la tabla de hechos (`Fact_Ventas`). Algunas de las medidas DAX implementadas incluyen:

* **Total de Ventas:**
  ```dax
  Total_Ventas = SUM(Fact_Ventas[total_venta])