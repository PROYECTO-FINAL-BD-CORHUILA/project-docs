# 07. Modelo Físico

El modelo físico representa la implementación real de la base de datos en el servidor de PostgreSQL. Para este proyecto, hemos utilizado **Liquibase** como herramienta de gestión de cambios para garantizar que el esquema sea versionado y replicable.

### Implementación Técnica
Toda la estructura de tablas, llaves primarias y foráneas se encuentra definida en el siguiente archivo de script SQL formateado para Liquibase:

* 🔗 [Ver Script de Creación de Tablas (db.changelog-1.0.sql)](PEGAR_AQUI_TU_URL_COPIADA)

> **Nota:** Este archivo se encuentra en el repositorio técnico `project-bd` y es ejecutado automáticamente al levantar el contenedor de Docker.
