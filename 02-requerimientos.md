02. Requerimientos del Sistema

Requerimientos Funcionales (RF)
* **RF01 - Registro de Productores:** El sistema debe permitir almacenar la información técnica de los caficultores, incluyendo su cédula cafetera.
* **RF02 - Gestión de Fincas:** Se debe registrar la ubicación y altitud de cada finca para garantizar la trazabilidad del origen.
* **RF03 - Control de Calidad (Catación):** El sistema debe permitir registrar los puntajes de catación (SCAA) de cada lote de café.
* **RF04 - Gestión de Inventario:** El sistema debe controlar la disponibilidad de sacos de café por cada lote.
* **RF05 - Procesamiento de Pedidos:** Los clientes deben poder generar pedidos vinculando múltiples lotes de café.

Requerimientos No Funcionales (RNF)
* **RNF01 - Persistencia de Datos:** El sistema utilizará PostgreSQL como motor de base de datos relacional.
* **RNF02 - Despliegue:** El entorno debe ser fácilmente replicable mediante contenedores Docker.
* **RNF03 - Versionamiento de Esquema:** Todo cambio estructural en la base de datos debe ser gestionado a través de Liquibase.
