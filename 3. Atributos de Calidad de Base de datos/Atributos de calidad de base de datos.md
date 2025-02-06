# Comparativa de Bases de Datos

## Cuadro Comparativo

| Atributo                         | Base de Datos Relacional | MongoDB                | Cassandra             | Redis                   | DynamoDB               | AWS RDS                | Google Cloud SQL      |
|-----------------------------------|--------------------------|------------------------|-----------------------|-------------------------|------------------------|------------------------|-----------------------|
| **Facilidad de Aprendizaje**      | ★★★★★                    | ★★★★☆                  | ★★★☆☆                 | ★★★★☆                   | ★★★☆☆                  | ★★★★★                  | ★★★★★                 |
| **Facilidad de Modelado de Datos**| ★★★★★                    | ★★★☆☆                  | ★★★☆☆                 | ★★★☆☆                   | ★★★☆☆                  | ★★★★★                  | ★★★★★                 |
| **Scalabilidad/Throughput**       | ★★★☆☆                    | ★★★★☆                  | ★★★★★                 | ★★★★★                   | ★★★★★                  | ★★★★☆                  | ★★★★☆                 |
| **Availability/Partition Tolerance** | ★★★★☆                   | ★★★★☆                  | ★★★★★                 | ★★★☆☆                   | ★★★★★                  | ★★★★★                  | ★★★★★                 |
| **Consistencia**                 | ★★★★★                    | ★★★★☆                  | ★★★☆☆                 | ★★☆☆☆                   | ★★★☆☆                  | ★★★★★                  | ★★★★★                 |
| **Soporte al Lenguaje**          | ★★★★★                    | ★★★★☆                  | ★★★☆☆                 | ★★★★☆                   | ★★★☆☆                  | ★★★★★                  | ★★★★★                 |
| **Prioridad Lectura/Escritura**  | ★★★★☆                    | ★★★★☆                  | ★★★★☆                 | ★★★★★                   | ★★★★☆                  | ★★★★☆                  | ★★★★☆                 |

## Definición de Atributos

### 1. Facilidad de Aprendizaje
Este atributo se refiere a lo fácil que es aprender a utilizar la base de datos. Se evalúa según la documentación disponible, la comunidad de usuarios y la simplicidad en la configuración y operaciones básicas.

**Ejemplo:** MySQL es considerado fácil de aprender debido a su amplia documentación y gran comunidad de soporte.

### 2. Facilidad de Modelado de Datos
Este atributo evalúa qué tan sencillo es modelar datos dentro de la base de datos. En bases de datos relacionales, esto puede implicar la creación de tablas, relaciones y claves foráneas, mientras que en bases de datos NoSQL puede involucrar colecciones o tablas flexibles.

**Ejemplo:** En MongoDB, el modelado de datos es flexible ya que no requiere un esquema fijo, lo que permite insertar documentos con diferentes estructuras.

### 3. Scalabilidad/Throughput
Este atributo mide la capacidad de la base de datos para manejar un gran volumen de operaciones (lecturas y escrituras) y escalar horizontalmente para mejorar el rendimiento a medida que aumentan los datos y la demanda.

**Ejemplo:** Cassandra es conocida por su capacidad para escalar horizontalmente y manejar grandes volúmenes de datos sin afectar el rendimiento.

### 4. Availability/Partition Tolerance (Teorema CAP)
Este atributo describe cómo la base de datos maneja la disponibilidad en caso de fallos en las particiones de la red. La base de datos puede priorizar la disponibilidad o la consistencia, según su implementación.

**Ejemplo:** DynamoDB y Cassandra son bases de datos que priorizan la disponibilidad y la tolerancia a particiones, asegurando que el sistema siga operativo incluso si se produce una desconexión temporal en algunas partes de la red.

### 5. Consistencia
La consistencia describe el nivel en el que todos los nodos de una base de datos distribuidas tienen los mismos datos al mismo tiempo, evitando leer datos inconsistentes.

**Ejemplo:** Las bases de datos relacionales como MySQL y PostgreSQL garantizan alta consistencia, asegurando que todos los nodos tengan los mismos datos inmediatamente después de una transacción.

### 6. Soporte al Lenguaje
Este atributo se refiere a los lenguajes de programación y las interfaces disponibles para interactuar con la base de datos. Las bases de datos que ofrecen drivers oficiales y una amplia gama de soporte en lenguajes populares tienen una mejor puntuación en este aspecto.

**Ejemplo:** Redis tiene soporte oficial para múltiples lenguajes, incluidos Python, JavaScript, Java y más, lo que facilita la integración.

### 7. Prioridad Lectura/Escritura
Este atributo describe si la base de datos está optimizada para operaciones de lectura o escritura. Algunas bases de datos están diseñadas para manejar lecturas rápidas, mientras que otras están optimizadas para escribir datos rápidamente.

**Ejemplo:** Redis está optimizado para operaciones de lectura/escritura rápidas en memoria, lo que lo convierte en una excelente opción para sistemas de alto rendimiento que requieren acceso rápido a datos.
