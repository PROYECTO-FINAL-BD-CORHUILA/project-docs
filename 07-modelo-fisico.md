# 07. Modelo Físico

El modelo físico representa la implementación real de la base de datos en PostgreSQL. Se utiliza **Liquibase** para el versionamiento del esquema.

### Código Fuente del Esquema (DDL)

A continuación se detalla el script SQL formateado para Liquibase que crea la estructura base del Marketplace de Café:

```sql
--liquibase formatted sql

--changeset santiago:1
CREATE TABLE productores (
    id_productor SERIAL PRIMARY KEY,
    nombre VARCHAR(100) NOT NULL,
    cedula_cafetera VARCHAR(20) UNIQUE,
    telefono VARCHAR(15),
    municipio VARCHAR(50) DEFAULT 'Neiva'
);

CREATE TABLE fincas (
    id_finca SERIAL PRIMARY KEY,
    id_productor INT NOT NULL,
    nombre_finca VARCHAR(100) NOT NULL,
    vereda VARCHAR(100),
    altitud_msnm INT,
    CONSTRAINT fk_productor FOREIGN KEY (id_productor) REFERENCES productores(id_productor)
);

-- (El resto de tablas se encuentran en el repositorio técnico project-bd)
