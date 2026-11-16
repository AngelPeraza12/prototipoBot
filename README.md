# BOT Central de Pagos — UNAL (Prototipo Interactivo)

## ¿Para qué sirve este archivo?
Este archivo (`prototipo_central_pagos.html`) es un **prototipo funcional e interactivo de interfaz web** diseñado para optimizar el proceso de liquidación de órdenes de pago en la Universidad Nacional.

Su objetivo principal es automatizar la construcción y validación de una trama estructurada que el liquidador debe copiar y pegar posteriormente en el apartado de Notas de la plataforma externa Central de Pagos para ejecutar o causar la orden sin errores de sintaxis ni reprocesos manuales.

>  Este prototipo es autocontenido (HTML, CSS y JavaScript en un solo archivo) y no requiere conexión a internet, servidores ni bases de datos para ejecutarse, creó netamente para ver la funcionalidad del mismo y cumplir con el entregable propuesto en la tarea de Análisis del proyecto para realizar una aplicación web
---

## ¿Cómo ejecutar el prototipo?
1. Descargue y descomprima el archivo `.zip` (si aplica).
2. Ubique el archivo **`prototipo_central_pagos.html`**.
3. Haga doble clic sobre el archivo para abrirlo en cualquier navegador web moderno (Google Chrome, Microsoft Edge, Mozilla Firefox o Safari).

---

## Funcionalidades Principales

### 1. Captura y Procesamiento de Datos de Entrada
* **Carga inteligente (`▶ Ejecutar`):** 
  * *Modo Simulación rápida:* Si se pulsa el botón **▶ Ejecutar** con los campos vacíos, el sistema carga automáticamente un caso de prueba completo con datos reales de ejemplo (Solicitante, Contrato, alerta de Estampilla, códigos contables y valores) para evaluar su funcionamiento inmediato.
  * *Extracción por fórmula:* Si se pega una cadena de fórmula proveniente de *Central de Pagos*, el algoritmo extrae automáticamente los códigos de Liquidación (`Liq.`), `Tipo`, `Concepto`, `CeCo` e `ICA`.
* **Selector de Estado:** Permite clasificar el flujo de operación entre `BOT`, `MANUAL` o `SINBOT`.

### 2. Línea de Pago y Clasificación Contable
* **Generación dinámica de línea de pago:** Al modificar el *N° de Pago*, *Planilla (PL)*, *Mes* o *Año*, la línea superior se actualiza en tiempo real.
* **Alternancia de modalidad (`PAGO N°` / `PAGO FINAL`):** Botones de cambio rápido que ajustan automáticamente el prefijo de la línea de pago según corresponda a un pago parcial o al pago final del contrato.
* **Validación de Centro de Costos (CeCo):** Al ingresar un código de CeCo (por ejemplo, `2111503`, `2010101` o `3040210`), la interfaz despliega automáticamente la dependencia universitaria y la actividad económica asociada.

### 3. Validación Financiera y Cálculos Auxiliares
* **Cálculo automático del Valor Neto:** Resta en tiempo real los *Descuentos* al *Valor de la Solicitud*, mostrando tanto el formato monetario legible (`$ 4.351.000`) como el valor limpio sin separadores (`4351000`) requerido por la trama.
* **Botón de descuento rápido (`499.000`):** Aplica con un solo clic el descuento estándar frecuente.
* **Herramientas auxiliares desplegables:** Calcula automáticamente las retenciones según las tarifas ICA (`0,00766`, `0,00966`, `0,01104`), muestra el tope de `32 UVT Max` y suma los aportes de **Salud y Pensión** (`Total SS`).

### 4. Generación y Copiado de la Trama Final
* **Ensamblaje en vivo:** Cada cambio realizado en los formularios reconstruye inmediatamente la cadena delimitada por barras verticales (`APROBADO|BOT|887818|...`) en el panel inferior.
* **Copiado directo (`📋 Copiar Trama`):** Copia la cadena exacta al portapapeles del sistema operativo con confirmación visual, dejándola lista para ser pegada en *Central de Pagos*.
* **Utilidades de interfaz:** Incluye botón **`Limpiar`** para reiniciar todos los campos a cero y botón **`🌙 Modo Noche / ☀️ Modo Día`** para adaptar el contraste visual durante jornadas prolongadas de trabajo.