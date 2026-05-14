03. Reglas de Negocio (Business Rules)

Estas reglas definen las restricciones y comportamientos automáticos que la base de datos debe garantizar para asegurar la calidad del café del Huila.

1. Integridad de la Calidad (Café Especial)
* BR01 - Puntaje Mínimo:Todo lote registrado como "Café Especial" debe contar con un puntaje de catación SCAA igual o superior a 80 puntos.
* BR02 - Catación Obligatoria: No se puede poner a la venta (estado 'Disponible') ningún lote que no tenga al menos un registro de catación asociado.

2. Gestión de Inventarios y Ventas
* BR03 - Stock No Negativo: La cantidad de sacos disponibles en un lote nunca puede ser menor a cero tras una venta.
* BR04 - Consistencia de Precios: El precio base del café se ajustará automáticamente según el puntaje de catación: a mayor puntaje, mayor será el recargo por calidad.

3. Trazabilidad y Origen
* BR05 - Vinculación de Finca: Un lote de café debe pertenecer obligatoriamente a una finca registrada, y esta a su vez debe estar vinculada a un productor con cédula cafetera vigente.
* BR06 - Unicidad de Lotes: No pueden existir dos lotes con el mismo código de trazabilidad para un mismo productor en la misma cosecha.
