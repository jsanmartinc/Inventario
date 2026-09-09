# 📦 Sistema PWA de Gestión de Inventarios y Ubicaciones de Bodega

![Versión](https://img.shields.io/badge/Versi%C3%B3n-1.0.0-blue)
![PWA](https://img.shields.io/badge/PWA-Ready-green)
![JavaScript](https://img.shields.io/badge/JavaScript-Vanilla-yellow)
![Licencia](https://img.shields.io/badge/Licencia-MIT-orange)

Aplicación Web Progresiva (PWA) de arquitectura Single Page Application (SPA) diseñada para optimizar la trazabilidad, el control de stock y la asignación de ubicaciones físicas (Piso / Pasillo / Nivel) en bodegas de e-Commerce y logística de repuestos.

---

## 💡 Origen y Motivación del Proyecto

Este proyecto nació de la experiencia práctica directa en el control de almacenes. Al operar sistemas ERP corporativos como **Odoo**, detecté una brecha operativa recurrente: **la curva de aprendizaje del software tradicional representa una barrera de entrada para operarios en terreno**, ralentizando la búsqueda de ítems y la inducción de nuevo personal.

### Evolución Iterativa del Producto
* **Fase 1 (Consulta Rápida):** Nació como una herramienta liviana para responder en segundos a la pregunta: *¿En qué lugar exacto está este repuesto?*
* **Fase 2 (Reglas de Negocio):** Se incorporó validación jerárquica (ej. prohibir asignar niveles o pasillos sin definir el piso) para eliminar errores de digitación en la bodega.
* **Fase 3 (Control e Inteligencia Operativa):** Evolucionó a un centro de control con dashboard de stock crítico, procesamiento masivo de datos en cliente y control de permisos (RBAC).

**Impacto:** Una solución mobile-first de adopción inmediata y cero costo de infraestructura que optimiza los tiempos de picking y búsqueda.

---

## 📸 Características Principales

* **Control de Ubicaciones Físicas:** Mapeo y asignación en tiempo real de productos a estructuras de almacenamiento (Piso, Pasillo, Nivel) con validación de jerarquía operativa.
* **Dashboard de Inteligencia Operativa:** 
  * Indicadores de salud de stock (Total, Ubicados vs. Sin Ubicar, Stock Bajo < 10 unidades, Sin Stock).
  * Reportabilidad automática del Top 10 de productos más consultados.
  * Alertas de reabastecimiento crítico.
* **Procesamiento Masivo de Datos (ETL Client-Side):** Carga, lectura y parsing de planillas Excel (`.xlsx`, `.csv`) directamente en el navegador mediante SheetJS sin saturar servidores externos.
* **Módulo de Autenticación y Permisos (RBAC):** Gestión de usuarios por roles (*Administrador*, *Editor*, *Visitante*) con control granular de acciones.
* **Trazabilidad y Auditoría:** Registro cronológico de transacciones con fecha, hora, usuario y acción para auditoría de inventario.
* **Soporte PWA Mobile-First:** Funcionalidad offline, instalable en colectores de datos/smartphones y diseño adaptativo con Modo Oscuro.

---

## 📋 Reglas de Negocio Implementadas

1. **Jerarquía Espacial de Almacén:** No es posible asignar un *Pasillo* o *Nivel* a un ítem sin registrar previamente el *Piso* correspondiente.
2. **Alertas de Reabastecimiento:** Identificación automática de productos con stock menor a 10 unidades para prevenir quiebres de inventario.
3. **Auditoría Protegida:** Las acciones críticas de limpieza o restablecimiento de base de datos requieren doble confirmación mediante clave maestra administrativa.

---

## 🛠️ Tecnologías Utilizadas

* **Front-End:** HTML5 Semántico, CSS3 Nativo (Variables CSS, Flexbox, Grid), JavaScript Vanilla (ES6+).
* **Persistencia de Datos:** `localStorage`, `sessionStorage`, manipulación de JSON.
* **Librerías Integradas:** [SheetJS (xlsx)](https://sheetjs.com/) para parsing e integración de hojas de cálculo.
* **PWA & Cache:** Service Workers (`sw.js`), Web App Manifest.
* **Metodología de Desarrollo:** Asistido mediante IA Generativa para la aceleración en la maquetación e implementación de componentes UI.

---

## 🚀 Instalación y Uso Local

1. Clona este repositorio:
   ```bash
   git clone [https://github.com/jsanmartinc/Inventario.git](https://github.com/jsanmartinc/Inventario.git)
