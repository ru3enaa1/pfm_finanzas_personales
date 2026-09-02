<div align="center">

# Pfm

**Tu dinero y el de tu negocio, en una sola cuenta.**

Finanzas personales y contabilidad de empresa conviviendo bajo el mismo inicio de
sesión: presupuestos, ahorro e informes por un lado; facturación, libros y
calendario DIAN por el otro. Sin que ninguna se meta con la otra.

[![Java](https://img.shields.io/badge/Java-17-orange?logo=openjdk)](https://openjdk.org/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.5.16-6DB33F?logo=spring)](https://spring.io/projects/spring-boot)
[![MySQL](https://img.shields.io/badge/MySQL-8-4479A1?logo=mysql)](https://www.mysql.com/)
[![Thymeleaf](https://img.shields.io/badge/Thymeleaf-3.1-005F0F?logo=thymeleaf)](https://www.thymeleaf.org/)
[![Pruebas](https://img.shields.io/badge/pruebas-1369-2F9E7E)](#pruebas)
[![OWASP](https://img.shields.io/badge/seguridad-auditada%20seg%C3%BAn%20OWASP-5B8DEF)](#seguridad)
[![Licencia](https://img.shields.io/badge/licencia-propietaria-C4985A)](#licencia)

</div>

---

## El problema

Quien tiene un negocio pequeño acaba mezclando la plata del bolsillo con la del
negocio. No por desorden: **porque las herramientas obligan a elegir.** Las
aplicaciones de finanzas personales no saben de IVA ni de retenciones; los
programas contables dan por hecho que ya tienes contador y no te preguntan cómo
vas de gastos este mes. La misma cuenta paga el mercado y al proveedor, y no hay
un sitio donde eso se vea.

Pfm no elige. Es **una cuenta con dos modos**, y se cambia de uno a otro con un
clic desde la barra superior.

---

## Los dos modos

### Modo Personal

Para llevar tu propia plata, sin abrir ninguna empresa.

| | |
|---|---|
| **Cuentas** | Bancarias, efectivo, tarjeta de crédito e inversión, con saldo derivado de sus movimientos |
| **Transacciones** | Ingresos, gastos y transferencias entre cuentas, con categorías y adjuntos |
| **Presupuestos** | Tope mensual por categoría, con barra de avance y aviso al acercarse al límite |
| **Fondos de ahorro** | Bolsas con meta anual, aportes desde tus cuentas y seguimiento mes a mes |
| **Informes** | Evolución mensual, gasto por categoría y comparativas, exportables a CSV, Excel y PDF |
| **Alertas** | Recordatorios de gastos fijos y avisos por correo |
| **Multimoneda** | COP, USD y EUR con conversión y tasa histórica |

### Modo Empresa

Contabilidad completa para una pyme colombiana, con validez fiscal.

| | |
|---|---|
| **Panel** | Caja disponible, ingresos, gastos y utilidad del período, con serie de seis meses |
| **Movimientos** | Ingresos y egresos con IVA y retenciones calculados según el régimen del tercero |
| **Facturación** | Emisión y numeración consecutiva, cotizaciones y notas |
| **Contabilidad** | Plan de cuentas editable, asientos automáticos y manuales, libros y balance de prueba |
| **Salud contable** | Seis comprobaciones cruzadas que dicen cuál no cuadra, **por cuánto** y dónde se arregla |
| **DIAN** | Calendario de vencimientos que se mueve con el dígito del NIT, retenciones y exógena |
| **Inventario** | Catálogo con costo y existencias, y kardex valorizado |
| **Activos fijos** | Alta, depreciación y baja |
| **Nómina** | Liquidación con sus aportes y provisiones |
| **Cierres** | Mensual —con carpeta lista para el contador— y anual |
| **Terceros** | Clientes y proveedores con su régimen y su documento |
| **Colaboradores** | Cinco roles: propietario, contador, auxiliar contable, revisor fiscal y socio en solo lectura |
| **Activos digitales** | Trazabilidad de cripto con score de origen de fondos |

### Lo que une a los dos

- **Capi**, un asistente que acompaña ambos modos y responde sobre tus propios datos.
- **Aislamiento por diseño.** Un colaborador ve la empresa a la que lo invitaste y
  nada más: nunca las finanzas personales de nadie. Hay pruebas dedicadas a que
  esa frontera no se mueva.
- **Enlace de auditor.** Una vista de solo lectura para el contador, con **token
  expirable y sin necesidad de cuenta**.

---

## Vienes de Excel

Cambiar de herramienta no debería costar la historia. Se importan cuatro cosas:

| | |
|---|---|
| **Clientes y proveedores** | Nombre, NIT y contacto |
| **Movimientos** | Ingresos y egresos con su fecha, valor e IVA |
| **Saldos iniciales** | El balance con el que llegas: caja, cartera, deudas y patrimonio |
| **Inventario** | Catálogo con costo y existencias |

Tú emparejas las columnas —nada se adivina cuando adivinar cambiaría un número—,
la importación dice **qué fila no pudo leer y por qué**, y si aun así sale mal,
**se deshace**.

---

## Planes

Al registrarte entras con **30 días de Pro incluidos**. Al terminar, la cuenta
vuelve a Free automáticamente y no se cobra nada.

| | **Free** | **Pro** | **Empresa** |
|---|---|---|---|
| Precio | $0, sin caducidad | $19.900 COP/mes | $69.900 COP/mes |
| Cuentas · presupuestos · fondos | 1 · 3 · 1 | Sin límite | Sin límite |
| Informes en pantalla | Sí | Sí | Sí |
| Exportación y alertas por correo | — | Sí | Sí |
| Capi | — | Sí | Sí |
| Modo Empresa | — | Sobre una **empresa de práctica** | Sobre **tu empresa real** |
| Invitar a tu contador | — | — | Sí |

> **Degradar no es despojar.** Si dejas de pagar, no se borra nada: la cuenta
> vuelve a Free y la empresa pasa a **solo lectura**. La sigues viendo entera y
> puedes exportar tus libros, tu inventario y tus movimientos. Lo que no puedes
> es seguir registrando hasta reactivar el plan.

Los precios se leen de la configuración en un único sitio, así que la página de
planes, el cobro y los datos estructurados del buscador **no pueden decir cifras
distintas**.

---

## Stack

| Capa | Tecnología |
|---|---|
| Lenguaje | Java 17 |
| Framework | Spring Boot 3.5.16 — Web, Data JPA, Security, Validation, Mail |
| Vistas | Thymeleaf 3.1 con `thymeleaf-extras-springsecurity6` |
| Base de datos | MySQL 8 |
| Documentos | Apache PDFBox · Apache POI |
| Construcción | Maven (wrapper incluido) |

Sin framework de front: HTML, CSS y JavaScript sin librerías. Las maquetas del
sitio público son HTML y CSS, no imágenes — pesan cero, se ven nítidas en
cualquier pantalla y no envejecen cuando la aplicación cambia.

### Dimensiones

| | |
|---|---|
| Código Java | ~48.600 líneas en 423 clases |
| Entidades | 52 |
| Servicios | 69 |
| Plantillas | 107 |
| Endpoints HTTP | 253 |
| Código de pruebas | ~36.700 líneas en 137 clases |
| Pruebas | **1.369** |

---

## Decisiones de diseño que vale la pena conocer

**El balance no se guarda: se deriva.** Sale de los asientos cada vez que se
pide, así que no existe el saldo desactualizado que hay que recalcular. Cuadra
por construcción.

**Una sola puerta por regla.** Quién entra al Modo Empresa se decide en un único
método. La regla llegó a estar escrita en tres sitios y el desajuste dejó entrar
al panel personal bajo el cromo de empresa; desde entonces, una regla, un sitio.

**Ninguna heurística decide sola algo que cambie un número.** En la importación,
una columna llamada «Valor» puede ser base o puede llevar el IVA dentro: las dos
lecturas dan cifras creíbles y una está mal en un 19%. Se pregunta.

**Salud contable no puntúa: señala.** No da una nota sobre 100 —que no se puede
accionar— sino la comprobación que falla, la diferencia exacta y el enlace a la
pantalla donde se arregla.

**El esquema se versiona a mano y es idempotente.** `ddl-auto` está en `none`.
Cada migración vive en `database/schema.sql` y puede volver a ejecutarse sin
romper nada.

---

## Pruebas

**1.369 pruebas, todas verdes con `clean`** — unas 36.700 líneas de código de
prueba para 48.600 de producción.

No son 1.369 comprobaciones de que un método devuelve lo que devuelve. Hay tres
familias, y cada una nació de un fallo real que la anterior no habría cogido.

### 1 · Lo que solo se ve mirando

Un defecto visual no rompe nada, así que ninguna prueba de dominio lo nota. **O se
fija con una prueba, o vuelve.**

| Prueba | Qué impide |
|---|---|
| `AislamientoPersonalTest` · `FronteraEntreModosTest` | Que un colaborador alcance datos personales, o que un modo pinte los del otro |
| `InvariantesPlanTest` | Que la escalera de planes se rompa y un plan superior pierda lo que ya tenía |
| `PagoIdempotenteTest` | Que un pago repetido cobre dos veces |
| `PlantillasSanasTest` | Comentarios mal cerrados y `confirm()` del navegador |
| `SeoTest` | Canónica que ignora la cabecera `Host`, JSON-LD válido y precios que no se duplican |
| `ContrasteAaTest` | Que un cambio de color deje texto por debajo del mínimo legible |
| `LandingComprobadoTest` | Anclas rotas, imágenes sin `alt`, títulos repetidos |
| `LogotipoSinDeformarTest` · `BarraSuperiorTest` | Dos defectos visuales reales que llegaron a producirse y no rompían nada |
| `ConfiguracionProduccionTest` | Que algo pensado para desarrollo se cuele en producción |

### 2 · Uso real, apartado por apartado

**236 casos** que recorren la aplicación *como la usa alguien*, con usuarios
desechables y por los mismos formularios que envía el navegador. Los 23 apartados
de los dos modos, más 13 recorridos completos.

Los casos se ordenan por **probabilidad de que un usuario llegue ahí**: lo que
hace todo el mundo, el uso normal, **el usuario que se equivoca** —la banda que
más defectos entrega— y lo raro pero grave.

Encontró siete defectos que las 1.085 pruebas de entonces no veían, entre ellos un
formato de moneda que **cambiaba según la máquina donde corriera el servidor** y
un mensaje técnico de la base de datos que llegaba a la pantalla del usuario.

### 3 · Seguridad, por clase de vulnerabilidad

<a name="seguridad"></a>Una campana distinta: no *dónde llega un usuario* sino
**por dónde entra un atacante**, ordenada por la prevalencia real del **OWASP
Top 10**.

| | Qué se comprueba |
|---|---|
| `PostsExigenCsrfTest` | Que las ~120 rutas que escriben **exijan su token**, y que ninguna atienda a un anónimo |
| `AislamientoEntreEmpresasTest` | Que una empresa no vea a otra, ni por pantalla, ni por sesión forzada, ni por export |
| `RecursosHijosAcotadosTest` | Que un soporte o una factura no se sirvan por su id a secas |
| `NadaSeInyectaEnLaPantallaTest` | XSS, en las 107 plantillas y en lo que devuelve el servidor |
| `CadenasDeAtaqueTest` | Siete cadenas completas: escalada de rol, robo de sesión, plan vencido |
| `NadaSensibleSeEscapaTest` | Que una contraseña no acabe nunca en el archivo de registro |
| `FormularioNoPrometeMasQueLaEntidadTest` | Que ningún formulario acepte más de lo que la base aguanta |

El proyecto pasó por un **proceso de refuerzo guiado por el OWASP Top 10**:
revisión capa por capa —configuración, controladores, servicios, repositorios,
plantillas y JavaScript—, pruebas dirigidas por clase de vulnerabilidad, y
cadenas de ataque que encadenan pasos que por separado no son nada.

Las dependencias se auditan con **OWASP dependency-check** contra la base del
NVD, y se mantienen al día: el trabajo de refuerzo incluyó actualizar el
framework, el servidor de aplicaciones y las bibliotecas de documentos.

---

## Puesta en marcha

Requisitos: **JDK 17** y **MySQL 8**.

```bash
# 1 · Base de datos
mysql -u TU_USUARIO -p < database/schema.sql

# 2 · Configuración local
cp src/main/resources/application.properties.example \
   src/main/resources/application.properties
#    …y edítalo con tus credenciales.

# 3 · Arrancar
./mvnw spring-boot:run          # http://localhost:8080

# 4 · Pruebas
./mvnw clean test
```

> `src/main/resources/application.properties` **no se versiona**: lleva
> credenciales. El fichero `.example` documenta cada clave que hace falta.

---

## Estado

**MVP completo, auditado y endurecido.** En ensayo de despliegue.

**Construido**

- Modo Personal y Modo Empresa, ambos operativos
- Los tres planes, con su cobro y su degradación
- Migración desde Excel de punta a punta
- Capi
- Sitio público: mensaje, planes, preguntas, páginas legales y SEO técnico

**Verificado**

- **Auditoría de uso** — 23 apartados y 13 recorridos, 236 casos. Los siete
  defectos que encontró, corregidos con su prueba.
- **Refuerzo de seguridad** — revisión por capa de código y pruebas por clase de
  vulnerabilidad, guiadas por el OWASP Top 10. Dependencias auditadas y al día.
- **Ensayo con el perfil de producción** — arranque, recorrido completo y
  configuración real verificados contra una base aparte.
- **Restauración de la copia de seguridad** — la base reconstruida desde cero
  solo con el respaldo: 52 tablas y 1.378 filas, todas coincidentes.

**Pendiente**

- Ensayo con HTTPS, para cerrar lo que sin TLS no puede probarse
- Verificación de correo antes del período de prueba

---

## Licencia

**Software propietario. Todos los derechos reservados.**

Copyright © 2026 Rubén Agudelo Alzate.

Este repositorio se publica con fines de **consulta y evaluación**. No se concede
licencia para usar, copiar, modificar, distribuir ni explotar comercialmente el
software ni ninguna parte de él. El texto completo y vinculante está en
[`LICENSE`](LICENSE).

Las bibliotecas de terceros conservan sus propias licencias, y ninguna de las
condiciones de arriba pretende alterarlas.

---

<div align="center">
<sub>Hecho en Colombia.</sub>
</div>
