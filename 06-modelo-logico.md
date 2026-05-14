# 06. Modelo Lógico

### 1. Tabla: **productores**
*   **id_productor**: PK, SERIAL
*   **nombre**: VARCHAR(100), NOT NULL
*   **cedula_cafetera**: VARCHAR(20), UNIQUE
*   **telefono**: VARCHAR(15)
*   **municipio**: VARCHAR(50)

---

### 2. Tabla: **fincas**
*   **id_finca**: PK, SERIAL
*   **id_productor**: FK -> productores.id_productor
*   **nombre_finca**: VARCHAR(100)
*   **altitud_msnm**: INT

---

### 3. Tabla: **lotes**
*   **id_lote**: PK, SERIAL
*   **id_finca**: FK -> fincas.id_finca
*   **variedad**: VARCHAR(50) -- Ej: Bourbon, Caturra, Geisha
*   **proceso**: VARCHAR(50) -- Ej: Lavado, Honey, Natural
*   **cantidad_sacos**: INT
*   **estado**: VARCHAR(20) -- Ej: Disponible, Vendido, En proceso

---

### 4. Tabla: **cataciones**
*   **id_catacion**: PK, SERIAL
*   **id_lote**: FK -> lotes.id_lote
*   **puntaje_scaa**: DECIMAL(4,2)
*   **notas_sabor**: TEXT
*   **fecha_catacion**: DATE

---

### 5. Tabla: **clientes**
*   **id_cliente**: PK, SERIAL
*   **nombre_empresa**: VARCHAR(100)
*   **pais**: VARCHAR(50)

---

### 6. Tabla: **pedidos**
*   **id_pedido**: PK, SERIAL
*   **id_cliente**: FK -> clientes.id_cliente
*   **fecha_pedido**: TIMESTAMP
*   **total_pago**: DECIMAL(12,2)

---

### 7. Tabla: **detalle_pedidos**
*   **id_detalle**: PK, SERIAL
*   **id_pedido**: FK -> pedidos.id_pedido
*   **id_lote**: FK -> lotes.id_lote
*   **cantidad_vendida**: INT
