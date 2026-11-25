# Analítica de un restaurante: PostgreSQL, Databricks y Power BI

## Contexto
Análisis de la base de datos de un restaurante ficticio (PostgreSQL en Neon) con
5 tablas: clientes, productos, sucursales, pedidos y detalle_pedido. Objetivo:
identificar los productos que impulsan las operaciones y comparar las sucursales
Centro y Norte.

## Preguntas que responde
1. ¿Cómo evoluciona mensualmente el importe de pedidos completados?
2. ¿Qué productos y categorías generan mayores importes por sucursal?
3. ¿Qué segmentos concentran más pedidos completados?

## Arquitectura (bronce, plata, oro)
- **Bronce:** copia de las 5 tablas de origen, sin cambios.
- **Plata:** limpieza (estados unificados, líneas inválidas a cuarentena,
  descuentos y segmentos corregidos).
- **Oro:** tablas listas para analizar: fact_ventas, ventas_mensuales,
  productos_por_sucursal, segmentos y comparacion_sucursales.

## Dashboard
Hecho en Power BI conectado a la capa oro de Databricks. Ver carpeta `dashboard/`.

## Hallazgos principales
- Centro y Norte están casi empatadas (diferencia menor al 1% en importe).
- La Pizza es el producto que más importe aporta en ambas sucursales; Platos
  concentra cerca del 78% del importe.
- El segmento Frecuente concentra más pedidos (297 de 761).
- El importe mensual cae entre nov 2024 y oct 2025 y se recupera en 2026
  (a validar con el negocio).
  
