# Principio ACID en Transacciones

El principio **ACID** define las propiedades esenciales que deben cumplir las transacciones en bases de datos para garantizar la confiabilidad y la integridad de los datos. Sus siglas representan:

1. **Atomicidad (Atomicity)**
2. **Consistencia (Consistency)**
3. **Aislamiento (Isolation)**
4. **Durabilidad (Durability)**

A continuación, se explican cada una de estas propiedades con ejemplos donde se cumplen y no se cumplen.

---

## 1. **Atomicidad**
Garantiza que una transacción se ejecute completamente o no se ejecute en absoluto. Si una parte de la transacción falla, toda la operación debe revertirse.

**Ejemplo donde se cumple:**
- Un sistema bancario realiza una transferencia de $100 de la Cuenta A a la Cuenta B.
  - Se resta $100 de la Cuenta A.
  - Se suman $100 a la Cuenta B.
  - Si alguna de las dos operaciones falla, la transacción se revierte.

**Ejemplo donde NO se cumple:**
- La Cuenta A se debita $100, pero antes de acreditar la Cuenta B, ocurre una falla del sistema.
  - Resultado: El dinero desaparece, lo que rompe la atomicidad.
  - Esto sucede cuando no hay un mecanismo de rollback o confirmación de transacción.

---

## 2. **Consistencia**
Garantiza que la base de datos pase de un estado válido a otro estado válido, sin violar restricciones de integridad.

**Ejemplo donde se cumple:**
- En una base de datos que exige que el saldo de una cuenta nunca sea negativo:
  - Si un cliente intenta retirar $500 de una cuenta con $300, la transacción es rechazada.
  - Esto mantiene la integridad de los datos.

**Ejemplo donde NO se cumple:**
- Si se permite el retiro de $500 de una cuenta con solo $300:
  - La base de datos termina en un estado inválido (saldo negativo sin autorización).
  - Esto ocurre cuando las reglas de negocio o restricciones no son respetadas.

---

## 3. **Aislamiento**
Asegura que las transacciones concurrentes no interfieran entre sí, evitando problemas como condiciones de carrera o lecturas inconsistentes.

**Ejemplo donde se cumple:**
- Dos usuarios intentan comprar el último producto en stock:
  - El sistema bloquea el producto cuando un usuario inicia la compra.
  - El segundo usuario recibe una notificación de que el producto ya no está disponible.

**Ejemplo donde NO se cumple:**
- Dos usuarios compran el mismo producto simultáneamente:
  - Ambos ven el producto disponible y completan la compra.
  - Solo hay un producto en stock, pero se procesan dos ventas.
  - Esto ocurre cuando no hay control de concurrencia adecuado (como bloqueos o niveles de aislamiento de transacción).

---

## 4. **Durabilidad**
Asegura que una vez que una transacción ha sido confirmada, sus cambios persistan en la base de datos incluso si hay fallos del sistema.

**Ejemplo donde se cumple:**
- Un cliente realiza una compra y el sistema confirma la transacción.
  - Aunque haya un corte de energía después de la confirmación, la compra sigue registrada cuando el sistema se reinicia.

**Ejemplo donde NO se cumple:**
- Un usuario transfiere dinero y recibe confirmación.
  - Poco después, el servidor falla y, tras el reinicio, la transacción desaparece.
  - Esto ocurre si los datos no se escriben en almacenamiento permanente antes de confirmar la transacción.

---

