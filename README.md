# Panel de Análisis de Ventas — Mercado Central

Dashboard interactivo que analiza el detalle transaccional de un supermercado ficticio (153.008 líneas de ticket, 4 centros, 282 referencias de producto), construido como proyecto de práctica en mi transición de jefe de supermercado a analista de datos, y ayudado por la IA.

🔗 **[![Vista previa del dashboard](docs/preview.png)](https://adnamantina-web.github.io/Analisis_tickets_compra/dashboard_ventas_marzo2024.html))**

![Vista previa del dashboard](docs/preview.png)
<img width="390" height="586" alt="image" src="https://github.com/user-attachments/assets/7278b5a8-a495-419a-b29b-787963291ce8" />
<img width="369" height="552" alt="image" src="https://github.com/user-attachments/assets/bcad8b69-2258-446d-a7ee-0bc8f63641ed" />
<img width="382" height="505" alt="image" src="https://github.com/user-attachments/assets/ae6f7667-14a1-4dcd-a9a4-0fb9b56cd9a2" />



---

## El proyecto

Durante años gestioné un supermercado tomando decisiones diarias —qué pedir, qué sección reforzar, qué referencia retirar— basadas en intuición construida a pie de tienda. Este proyecto traduce ese tipo de preguntas a un análisis de datos real:

- ¿Qué productos sostienen realmente la facturación, y cuáles parecen importantes pero no lo son?
- ¿Dónde se concentra la baja rotación, y qué referencias son candidatas a retirar?
- ¿Hay diferencias relevantes de mix de producto entre centros, o el comportamiento es homogéneo?
- ¿Qué patrones de estacionalidad (día de la semana, fecha) afectan al ticket medio?
- ¿Cómo impactan las promociones y descuentos al comportamiento de compra?

Los datos son **ficticios**, generados con fines de práctica, pero el detalle (a nivel de línea de ticket, no agregados) y el tipo de preguntas que resuelve son los mismos que en un caso real de retail.

## Qué incluye el dashboard

El panel se organiza en 6 bloques de análisis, cada uno con su lectura de negocio:

| Bloque | Qué responde |
|---|---|
| **Productos** | Ranking de productos por importe y unidades; qué referencias son top y cuáles son cola de catálogo |
| **Cesta de compra** | Composición media del ticket, unidades por cesta, productos que se compran juntos |
| **Centros** | Comparativa de ventas y ticket medio entre los 4 centros |
| **Promociones** | Efecto de descuentos y promociones sobre el volumen de venta |
| **Estacionalidad** | Patrones por día de la semana y evolución a lo largo del periodo |
| **Mix de producto** | Peso de cada sección/categoría por centro, y si hay especialización geográfica |

Cada bloque combina gráficas (Chart.js) con una lectura en lenguaje de negocio, no solo visualización.

## Estructura del repositorio

```
.
├── dashboard_ventas_marzo2024.html   # Dashboard final, autocontenido — ábrelo directamente en el navegador
├── notebook/
│   └── panel_ventas_mercado.ipynb       # Notebook (Google Colab) que regenera el dashboard desde el CSV original
├── data/
│   ├── ventas_ticket_decimales.csv   # Dataset original de detalle de ticket
│   └── dashboard_data.json           # Agregados ya calculados, en el formato que consume el dashboard

```

**El archivo que importa para verlo funcionar es `dashboard_ventas_marzo2024.html`** — no necesita servidor, instalación ni dependencias: se abre directamente en cualquier navegador moderno.

El resto de archivos (`notebook/`, `data/`, `src/`) documentan **cómo se construyó**: el notebook parte del CSV en bruto, calcula los 6 bloques de agregados, los inyecta en la plantilla HTML junto con `app.js`, y genera el archivo final descargable.

## Cómo reproducirlo desde cero

1. Abre `notebook/panel_venas_mercado_central.ipynb`en google colab.
2. Sube `data/ventas_ticket_decimales.csv` cuando el notebook lo solicite.
3. Ejecuta las celdas en orden: carga → limpieza → cálculo de agregados → ensamblado del HTML.
4. La última celda descarga automáticamente el dashboard final en un único archivo `.html`.

## Stack técnico

- **Análisis y preparación de datos:** Python (pandas), en notebook de Google Colab
- **Visualización:** Chart.js
- **Frontend:** HTML, CSS y JavaScript puro — sin frameworks, sin build, sin backend
- **Salida:** archivo único autocontenido, pensado para máxima portabilidad (se puede compartir, abrir offline, o desplegar en GitHub Pages sin configuración adicional)

## Sobre este proyecto

Este es el primer proyecto de mi portfolio de transición de jefe de supermercado a analista de datos en el que he utilizado la IA en casi todos los pasos. Llevo más de un año formándome en análisis de datos, y este caso de práctica busca demostrar algo concreto: sé qué preguntas de negocio hacerle a los datos porque las he vivido desde dentro de la operación, no solo desde la teoría, y salvar pasos tecnicos en los que estoy mejorando.

Más proyectos próximamente.

📫 Contacto: [armillas1976@gmail.com] · [(https://www.linkedin.com/in/bego%C3%B1a-armillas-alonso-b31a0562/)]

---

*Nota: los datos utilizados son ficticios y se generaron exclusivamente con fines de práctica y aprendizaje. No representan ventas, productos ni operaciones reales de ningún establecimiento.*
