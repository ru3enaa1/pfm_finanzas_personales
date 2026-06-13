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

A futuro PFM ofrece también un **Modo Empresa** dedicado a emprendedores y pymes en Colombia: facturación electrónica, calendario fiscal DIAN, reportes financieros y trazabilidad de activos digitales (cripto/CBDC). El usuario alterna entre Modo Personal y Modo Empresa con un solo click desde la barra superior, manteniendo una experiencia continua dentro de la misma app.

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
| Modo Empresa | — | Próximamente | Acceso completo |

El plan EMPRESA estará disponible una vez se complete la fase de desarrollo y validación del módulo. Cuando se libere, los usuarios PRO podrán alternar a Modo Empresa con un toggle desde la app sin necesidad de un plan adicional.

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

## Modo Empresa — en construcción

PFM Empresa extiende la app personal con un módulo contable orientado al emprendedor colombiano. La interfaz ya está scaffolded y el usuario puede previsualizarla; la implementación funcional de cada apartado llega en fases sucesivas.

Apartados planeados:

| | Módulo | Para qué sirve |
|---|---|---|
| 🏠 | **Panel** | KPIs del negocio de un vistazo: caja, ingresos, gastos, utilidad, próximo impuesto que vence |
| ↕ | **Movimientos** | Lista única de ingresos y gastos del negocio con categorización fiscal e IVA automático |
| 📄 | **Facturación** | Emisión de facturas electrónicas vía proveedor tecnológico autorizado por DIAN |
| 📆 | **DIAN / Impuestos** | Calendario tributario + cálculo automático de IVA y retenciones + carpeta DIAN anual |
| 💬 | **Guía / Asistente** | Copiloto para emprendedores sin formación contable: explica términos, recuerda vencimientos, evalúa salud fiscal |
| 👥 | **Terceros** | Agenda de clientes y proveedores con NIT y régimen tributario |
| 📊 | **Reportes** | Estado de Resultados, Balance General, Flujo de Caja en cualquier momento |
| ⬢ | **Activos digitales** | Trazabilidad de cripto (USDC, USDT, BTC) y CBDC: costo base, ganancias realizadas, certificado de origen lícito |
| ⚙ | **Configuración fiscal** | RUT, régimen tributario, periodicidad de IVA, actividad económica CIIU |

**Visión central**: que el empresario use el módulo sin necesidad de saber contabilidad, mientras el sistema mantiene su información lista para presentar a la DIAN y demostrar que su dinero es **limpio, soportado y suyo**.

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

### Corto plazo (próximas iteraciones)
- 💳 **Pasarela de pago real** (Stripe / Mercado Pago) reemplazando el checkout mock actual
- 🔑 **Recuperación de contraseña por email** para usuarios que pierden el acceso
- 📜 **Historial de pagos visible en /perfil**
- 🔐 **Verificación en dos pasos opcional** (TOTP con Google Authenticator)
- 📊 **Fase 0 del Modo Empresa**: entidad Empresa, selector activo en la barra, panel funcional

### Mediano plazo
- 🧾 **Fase 1 del Modo Empresa**: facturación electrónica DIAN vía proveedor autorizado + movimientos con IVA
- 📋 **Fase 2 del Modo Empresa**: calendario tributario funcional + reportes (Estado de Resultados, Balance, Flujo de Caja)
- 💱 **Fase 3 del Modo Empresa**: activos digitales con trazabilidad on-chain

### Largo plazo
- 🤖 **Asistente IA financiero** contextualizado al estado real del usuario
- 📱 **App móvil nativa** complementaria
- 🔗 **Integración bancaria** vía Open Banking
- 🏢 **Multi-usuario y roles** dentro de una misma empresa (equipos pequeños)

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
