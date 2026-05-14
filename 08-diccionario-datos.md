# 08. Diccionario de Datos

Este documento describe la estructura detallada de las 7 tablas que componen la base de datos del **Marketplace de Café Especial**.

---

### 1. Tabla: `productores`
| Campo | Tipo | Restricción | Descripción |
| :--- | :--- | :--- | :--- |
| **id_productor** | SERIAL | PK | Identificador único autoincremental. |
| **nombre** | VARCHAR(100) | NOT NULL | Nombre completo del productor. |
| **cedula_cafetera** | VARCHAR(20) | UNIQUE | Documento de identificación gremial. |
| **telefono** | VARCHAR(15) | - | Número de contacto. |
| **municipio** | VARCHAR(50) | DEFAULT 'Neiva' | Ubicación principal en el Huila. |

### 2. Tabla: `fincas`
| Campo | Tipo | Restricción | Descripción |
| :--- | :--- | :--- | :--- |
| **id_finca** | SERIAL | PK | Identificador único de la finca. |
| **id_productor** | INT | FK | Relación con el productor dueño del predio. |
| **nombre_finca** | VARCHAR(100) | NOT NULL | Nombre de la propiedad. |
| **vereda** | VARCHAR(100) | - | Ubicación rural específica. |
| **altitud_msnm** | INT | - | Altura sobre el nivel del mar. |

### 3. Tabla: `lotes`
| Campo | Tipo | Restricción | Descripción |
| :--- | :--- | :--- | :--- |
| **id_lote** | SERIAL | PK | Identificador único del lote. |
| **id_finca** | INT | FK | Finca de origen del café. |
| **variedad** | VARCHAR(50) | - | Tipo de café (Caturra, Borbón, etc.). |
| **proceso** | VARCHAR(50) | - | Método de beneficio (Lavado, Natural, etc.). |
| **cantidad_sacos** | INT | - | Stock disponible en bodega. |
| **estado** | VARCHAR(20) | - | Estado (Disponible, Vendido, En proceso). |

### 4. Tabla: `cataciones`
| Campo | Tipo | Restricción | Descripción |
| :--- | :--- | :--- | :--- |
| **id_catacion** | SERIAL | PK | Identificador de la sesión de catación. |
| **id_lote** | INT | FK | Lote evaluado sensorialmente. |
| **puntaje_scaa** | DECIMAL(4,2) | - | Calificación técnica (80+ es especial). |
| **notas_sabor** | TEXT | - | Perfil de taza (Notas de sabor). |
| **fecha_catacion** | DATE | DEFAULT TODAY | Fecha del registro de calidad. |

### 5. Tabla: `clientes`
| Campo | Tipo | Restricción | Descripción |
| :--- | :--- | :--- | :--- |
| **id_cliente** | SERIAL | PK | Identificador del comprador/empresa. |
| **nombre_empresa** | VARCHAR(100) | NOT NULL | Razón social del cliente interesado. |
| **pais** | VARCHAR(50) | - | País de destino del café. |

### 6. Tabla: `pedidos`
| Campo | Tipo | Restricción | Descripción |
| :--- | :--- | :--- | :--- |
| **id_pedido** | SERIAL | PK | Número único de orden de compra. |
| **id_cliente** | INT | FK | Cliente que realiza la compra. |
| **fecha_pedido** | TIMESTAMP | DEFAULT NOW | Fecha y hora exacta de la transacción. |
| **total_pago** | DECIMAL(12,2) | - | Monto total facturado. |

### 7. Tabla: `detalle_pedidos`
| Campo | Tipo | Restricción | Descripción |
| :--- | :--- | :--- | :--- |
| **id_detalle** | SERIAL | PK | Identificador de la línea del pedido. |
| **id_pedido** | INT | FK | Vínculo con la cabecera del pedido. |
| **id_lote** | INT | FK | Lote específico vendido. |
| **cantidad_vendida** | INT | - | Cantidad de sacos comprados. |
