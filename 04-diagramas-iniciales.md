# 04. Diagramas Iniciales

En esta fase preliminar, estructuramos gráficamente cómo interactúan las entidades principales del **Marketplace de Café Especial** antes de su normalización en el modelo lógico.

## Diagrama Entidad-Relación (Borrador Conceptual)

El siguiente diagrama ilustra el flujo básico del negocio, desde el cultivo por parte de los caficultores hasta la compra por parte de los clientes.

```mermaid
erDiagram
    PRODUCTORES ||--o{ FINCAS : "posee"
    FINCAS ||--o{ LOTES : "produce"
    LOTES ||--o| CATACIONES : "es evaluado en"
    CLIENTES ||--o{ PEDIDOS : "realiza"
    PEDIDOS ||--|{ DETALLE_PEDIDOS : "contiene"
    LOTES ||--o{ DETALLE_PEDIDOS : "es incluido en"

    PRODUCTORES {
        string cedula_cafetera
        string nombre
    }
    FINCAS {
        string nombre_finca
        int altitud
    }
    LOTES {
        string variedad
        int cantidad_sacos
    }
    CATACIONES {
        float puntaje_scaa
    }
    CLIENTES {
        string nombre_empresa
    }
    PEDIDOS {
        date fecha
    }
