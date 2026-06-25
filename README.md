<div align="center">

# PFM · Personal Finance Management

**Una plataforma de finanzas pensada para Latinoamérica con proyección europea.**

[![Java](https://img.shields.io/badge/Java-17-orange?logo=openjdk)](https://www.oracle.com/java/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.x-6DB33F?logo=spring)](https://spring.io/projects/spring-boot)
[![MySQL](https://img.shields.io/badge/MySQL-8-4479A1?logo=mysql)](https://www.mysql.com/)
[![Thymeleaf](https://img.shields.io/badge/Thymeleaf-3-005F0F?logo=thymeleaf)](https://www.thymeleaf.org/)

</div>

---

## ¿Qué es PFM?

PFM es una aplicación web de gestión financiera que combina **simplicidad de Nubank**, **claridad de Apple Cash** y **rigor de YNAB** para darle al usuario el control real de su dinero en una sola pantalla.

Diseñada para usuarios hispanohablantes — sin tecnicismos contables, sin curva de aprendizaje, sin fricción.

```
┌─────────────────────────────────────────────────┐
│  💰 Saldo                    $ 4,250,000  COP   │
│                                                 │
│  ╴ Este mes ╴      ╴ Filtrar ╴                  │
│  +2,300,000 ingresos              8 movimientos │
│  -1,150,000 gastos                              │
└─────────────────────────────────────────────────┘
```

PFM incluye además un **Modo Empresa** completo y funcional, dedicado a emprendedores y pymes en Colombia: panel del negocio, movimientos con IVA automático, terceros, calendario fiscal DIAN, facturación, reportes financieros, trazabilidad de activos digitales (cripto) y una Guía del Emprendedor gamificada. El usuario alterna entre Modo Personal y Modo Empresa con un solo click desde la barra superior, manteniendo una experiencia continua dentro de la misma app. Un copiloto global ("Capi") acompaña ambos modos.

---

## Planes

PFM funciona con un modelo **freemium**: el usuario empieza con 30 días de PRO al registrarse y, si decide no pagar, queda en un plan FREE indefinido con lo esencial para no perder sus datos.

| | **FREE** | **PRO** | **EMPRESA** |
|---|---|---|---|
| Precio | $0 indefinido | $9.900 COP / mes | Próximamente |
| Cuentas | 1 | Ilimitadas | — |
| Presupuestos | 3 activos | Ilimitados | — |
| Bolsas de ahorro | 1 | Ilimitadas | — |
| Transacciones | Ilimitadas | Ilimitadas | — |
| Informes en pantalla | Sí | Sí | — |
| Exportación CSV / PDF | — | Sí | — |
| Alertas por email | — | Sí | — |
| Multimoneda | Solo COP | COP / USD / EUR | — |
| Modo Empresa | — | Incluido (toggle) | Acceso completo |

El **Modo Empresa ya está construido y operativo**, accesible para usuarios PRO con un toggle desde la barra superior, sin plan adicional. El plan EMPRESA dedicado (multi-usuario, soporte y funciones avanzadas) se libera al completar las fases técnicas finales (facturación electrónica real con CUFE, partida doble).

---

## Modo Personal — lo que ya está construido

### 🏦 Cuentas financieras
- Tipos: corriente, ahorro, tarjeta de crédito, efectivo, inversión
- Cuenta activa global desde la barra superior — toda la app se adapta al contexto seleccionado
- Recálculo automático del saldo con cada movimiento

### 💸 Transacciones
- Modal de registro **simplificado estilo Apple Cash** — solo monto y categoría
- Vinculación opcional a presupuestos para tracking automático
- Timeline agrupado por fecha con filtros (Hoy / Semana / Mes / Todo) y categoría
- Conversión de divisa en tiempo real sin alterar datos históricos

### 📊 Presupuestos inteligentes
- **Dos tipos en uno**: límite mensual variable (Mercado, Salidas) o pago fijo recurrente (Arriendo, Netflix)
- Barras horizontales con código de color gradual: verde → amarillo → naranja → rojo
- Click directo para añadir un gasto al presupuesto sin salir del módulo
- Contexto dual estilo YNAB: límite global Y aporte de la cuenta activa

### 🎯 Fondos de ahorro (bolsas)
- Metas anuales (Vacaciones, Vehículo, Casa propia, etc.)
- Aportes generan transacciones reales — el saldo baja, refleja realidad
- Indicador "Meta alcanzada" con glow dorado al 100%
- Archivado en lugar de borrado: los aportes históricos se preservan

### 📈 Informes y analítica
- Dashboard agregado de todas las cuentas del usuario
- Selector global de período (Esta semana / Este mes / Este año)
- 4 visualizaciones complementarias: línea temporal, dona de distribución, barras diarias y KPIs clave
- KPIs: ahorro neto con delta vs período anterior, tasa de ahorro, progreso fondos, consumo presupuestos
- **Exportación CSV y PDF** (PRO) con 4 tipos de informe

### 🔔 Alertas y recordatorios
- Campana en la barra superior con badge de no leídas, visible desde cualquier vista
- Inbox cronológico con código de color por severidad (info / warn / crítica)
- Configuración en 2 columnas: Alertas reactivas + Recordatorios proactivos
- **Alertas críticas siempre activas** (saldo bajo, presupuesto sobrepasado)
- Anti-spam interno: misma alerta no se duplica en menos de 60 minutos
- **Email opcional** (PRO) cuando el usuario configura SMTP

### 🌍 Multi-divisa (PRO)
- Cambio entre **COP, USD y EUR** desde un chip en la barra superior
- Saldos, transacciones y presupuestos se reconvierten al instante
- Almacenamiento siempre en moneda base — sin ambigüedades históricas

### 🎨 Tema claro / oscuro
- Toggle sol/luna en la barra superior
- Preferencia persistente del usuario, sobrevive entre sesiones
- Cero parpadeo al cambiar de página

### 👤 Configuración de cuenta
- Página `/perfil` estilo Nubank con tarjetas apilables
- Editar nombre y apellido
- **Cambio de email** en 2 pasos con código de verificación (OTP de 6 dígitos al nuevo correo, expira en 15 minutos)
- **Cambio de contraseña** con medidor de fortaleza visual (rojo/amarillo/verde/dorado) y verificación de coincidencia
- **Eliminar cuenta** con doble confirmación (escribir correo + contraseña) — borra todos los datos en cascada
- Estado del plan visible con días restantes + acciones Activar / Renovar / Cancelar

### 🔐 Seguridad
- Autenticación con cifrado BCrypt
- Protección CSRF en todos los formularios (incluido el cierre de sesión)
- Validación contra acceso indebido en cada endpoint
- Códigos de verificación se almacenan únicamente en formato hash, nunca en texto plano
- Rate-limit entre solicitudes de OTP para prevenir abuso

---

## Modo Empresa — construido y operativo

PFM Empresa extiende la app personal con un módulo contable orientado al emprendedor colombiano. Los apartados siguientes **ya están construidos y funcionan con datos reales** (base de caja, motor fiscal por país). Lo que opera con interfaz final hoy:

### 🏠 Panel del negocio
- KPIs reales del mes: caja disponible, ingresos, gastos, utilidad, IVA neto a pagar
- Próximo vencimiento tributario y **salud fiscal** (score 0–100) de un vistazo
- Gráfico de ingresos vs. gastos de los últimos 6 meses

### ↕ Movimientos
- Registro de ingresos y gastos con **categorización fiscal** (gravado / exento / excluido) e **IVA automático** (motor fiscal Strategy por país — Colombia)
- Cuentas por cobrar / por pagar (CxC/CxP) y pulso de caja diario
- **Soportes adjuntos** (PDF/JPG/PNG): un gasto soportado queda listo para la DIAN

### 👥 Terceros
- Agenda de clientes y proveedores con NIT, régimen tributario y tipo
- Saldos por tercero y ficha de detalle; alimenta el cálculo de impuestos

### 📆 DIAN / Impuestos
- Calendario tributario con línea de tiempo anual y obligaciones por estado
- Liquidación automática de IVA a partir de los movimientos
- **Carpeta DIAN** descargable (ZIP con PDF resumen + CSV) y salud fiscal accionable

### 📄 Facturación
- Cuentas de cobro / facturas de venta con **numeración consecutiva**, IVA y PDF
- Al emitir genera el **ingreso enlazado y soportado** en Movimientos automáticamente
- *E6-ready*: la factura electrónica real con CUFE vía proveedor tecnológico autorizado es la siguiente fase (el modelo de datos ya está preparado)

### ⬢ Activos digitales — "Bóveda"
- Tesorería cripto (BTC, ETH, USDC, USDT, SOL, POL) **valorada en pesos**
- **Motor FIFO**: costo base y ganancia/pérdida realizada por venta
- Trazabilidad on-chain, **Score "Origen Verificado"**, **Certificado de trazabilidad** (PDF con sello SHA-256), **Snapshot 31-dic** y **Modo Auditor** (enlace de solo lectura para el contador)

### 📊 Reportes — "Radiografía del negocio"
- **Estado de Resultados**, **Posición financiera** y **Flujo de Caja** en una sola pantalla
- Selector de período, exportación CSV/PDF y compartir como documento formal (banco / socio / contador)

### 💬 Guía / Asistente
- **Guía del Emprendedor gamificada**: ruta de 8 capítulos, racha semanal, simulacro DIAN, insignias y checklist legal vivo — la gamificación se deriva del estado **real** del negocio
- **Capi**, copiloto global presente en **toda la app** (Personal y Empresa)

**Visión central**: que el empresario use el módulo sin necesidad de saber contabilidad, mientras el sistema mantiene su información lista para presentar a la DIAN y demostrar que su dinero es **limpio, soportado y suyo**.

> **Honestidad de producto:** lo construido opera en base de caja con datos reales y etiquetado honesto. La factura electrónica con CUFE, el Balance General NIIF (partida doble) y la IA real de Capi son fases técnicas siguientes — nunca se muestran datos inventados ni sellos oficiales falsos.

---

## Stack tecnológico

| Capa | Tecnología |
|---|---|
| **Lenguaje** | Java 17 |
| **Framework** | Spring Boot 3.x (Web + Security + Data JPA + Mail) |
| **ORM** | Hibernate 6 |
| **Base de datos** | MySQL 8 |
| **Plantillas** | Thymeleaf 3 |
| **Frontend** | HTML5 + CSS3 modular con tokens + Vanilla JS |
| **Charts** | Chart.js 4 |
| **PDF** | Apache PDFBox 3.0 |

---

## Arquitectura

PFM está construido como un **monolito modular** con separación por capas (Controller → Service → Repository → Database) y agrupación por dominio. El sistema de tematización (claro/oscuro) y el cambio de modo (Personal/Empresa) viven en una capa transversal de preferencias del usuario que se propaga a todas las vistas vía cookies y atributos de página, lo que da una experiencia continua sin recargas costosas ni estado fantasma entre sesiones.

El plan freemium se centraliza en un único `PlanService` que calcula el plan efectivo de cada usuario considerando whitelist familiar, tier activo y fecha de vencimiento del PRO. Cualquier nueva funcionalidad solo consulta a ese servicio para decidir si está disponible para el usuario actual, manteniendo la lógica de tier en un solo lugar.

---

## Roadmap

### Ya construido ✅
- **Modo Personal completo** (cuentas, transacciones, presupuestos, fondos, informes, alertas, multidivisa, perfil)
- **Modo Empresa E0–E5**: Panel, Movimientos (IVA automático), Terceros, DIAN/Impuestos (+ carpeta DIAN), Facturación, Activos digitales (FIFO + certificado + auditor), Reportes y Guía del Emprendedor
- **Capi**, copiloto global en toda la app (respuestas guiadas)

### Próximo (técnico)
- 🧾 **Facturación electrónica real (CUFE)** vía proveedor tecnológico autorizado por la DIAN
- 📚 **Partida doble + Balance General NIIF** (hoy reportes en base de caja)
- 💱 **Cripto F2/F3**: precios en vivo (CoinGecko) y verificación on-chain real
- 🎮 **Guía — fases siguientes**: empresa de práctica (demo), detección automática de misiones, certificados compartibles
- 🤖 **Capi con IA real** (Claude API) contextualizado al estado financiero del usuario
- 💳 **Pasarela de pago real** (Wompi / Stripe) y desbloqueos por logro

### Largo plazo
- 📱 **App móvil nativa** complementaria
- 🌎 **Multi-país** (SAT / SUNAT / SII / AEAT) — el motor fiscal ya es extensible por país
- 🔗 **Integración bancaria** vía Open Banking y conciliación automática
- 🏢 **Multi-usuario y roles** dentro de una misma empresa + **nómina electrónica**

---

## Licencia

**Software propietario — © 2026 Rubén Agudelo Alzate. Todos los derechos reservados.**

Este repositorio se publica con fines de **portafolio y demostración**. El código se puede
visualizar para evaluación profesional, pero **no se permite** su uso, copia, modificación,
distribución ni la reutilización de su lógica de negocio o conceptos de producto sin
autorización escrita del autor. Ver [LICENSE](LICENSE) para los términos completos.

Nació como proyecto productivo del programa Tecnología en Análisis y Desarrollo de Software
(ADSO); su condición formativa no altera la titularidad del autor. Las marcas y nombres de
terceros referenciados pertenecen a sus respectivos propietarios.

---

<div align="center">

*Construido con Spring Boot y atención al detalle. Pensado para escalar.*

</div>
