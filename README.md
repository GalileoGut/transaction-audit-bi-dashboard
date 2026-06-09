# Transaction-Audit-Dashboard-
Dashboard desarrollado para auditoría y análisis de transacciones en la plataforma de Rappi, identificando patrones de riesgo y anomalías en operaciones.
<p align="center">
  <img src="Captura_Rappi_Auditoria.png" width="800" height="500">
</p>

> 🚀 **[CLICK ACÁ PARA ACCEDER AL DASHBOARD INTERACTIVO](https://app.powerbi.com/onedrive/open?pbi_source=ODSPViewer&driveId=b!wF6ElwUz0UWkESkGPuSdBNWYtEuF7QFLnu4yZYCLF6l8rbnh0SxoTI66SYeviN4k&itemId=01XBJVBUTVGRSFHQLYSFA2NHHH3HF37TZS)**

---

## 📝 Descripción del Proyecto
Dashboard de Business Intelligence enfocado en Auditoría Financiera y Gestión de Riesgo Corporativo. La solución centraliza y analiza los flujos de dinero de múltiples plataformas de pago (ERP, MODO, RappiPay) para monitorear desvíos de presupuesto, controlar gastos y detectar anomalías operativas.

---

## 🛠️ Estructura y Origen de los Datos
El set de datos auditado contiene el historial de transacciones de la empresa con las siguientes dimensiones clave:
* `id_transaccion`: Identificador único de la operación.
* `fecha` y `monto`: Registro temporal y valor económico de la transacción.
* `usuario`: Empleado responsable del gasto.
* `proveedor` y `categoria`: Destino del dinero (Amazon, Rappi, Shell / Tecnología, Viáticos, Insumos).
* `status`: Estado de control (`completado`, `anómalo`, `DUPLICADO`).
* `sistema_origen`: Plataforma donde se inició el movimiento (ERP, MODO, RappiPay).

---

## 📊 Ingeniería de Datos y Reglas de Negocio
Para sanear el flujo financiero y armar las métricas del reporte, se modelaron las siguientes lógicas de negocio:

* **Métrica de Riesgo Transaccional (16.00%):** KPI diseñado para aislar el volumen de operaciones con estado `anómalo`. El modelo detectó que 8 de cada 50 transacciones totales presentaban desvíos sospechosos o montos fuera del estándar en categorías críticas.
* **Depuración de Duplicados:** Identificación y filtrado de registros clonados (mismo ID con estado `DUPLICADO`) en los cierres de conciliación de MODO y ERP que inflaban el presupuesto de forma ficticia.
* **Consolidación Multi-canal:** Homogeneización de formatos de fecha y nomenclatura de proveedores para unificar pasarelas independientes en una única base de auditoría centralizada.

---

  Componentes Clave del Reporte
*KPis Principales:** Visualización directa del porcentaje de riesgo operacional (16%) y alertas activas.
*Suma de Monto por Sistema de Origen:** Análisis del volumen de dinero que mueve cada pasarela, liderado por el ERP.
*Evolución Temporal:** Gráfico de líneas para auditar la tendencia del gasto corriente y detectar picos inusuales.
*Ranking de Proveedores de Riesgo:** Distribución de anomalías concentrada en plataformas
