# Planeación del Sistema


---

## 1. Épica

| Campo | Descripción |
|------|-------------|
| **ID** | EP-01 |
| **Título** | Funcionamiento general de la plataforma bankify (requerimientos funcionales) |
| **Descripción** | Bankify necesita esta épica para permitir que un cliente pueda diversas operaciones basadas en su cuenta de bankify. |
| **Stakeholder** | Clientes de Bankify (usuario final) y Gerente de Operaciones (quien necesita validar el modelo de negocio con funcionalidades esenciales). |

---

## 2. Historias de usuario

### HU-01

| Campo | Descripción |
|------|-------------|
| **ID** | HU-01 |
| **Título** | Consultar saldo de una cuenta |
| **Descripción** | Como **cliente**, quiero **consultar el saldo de mi cuenta**, para **conocer cuánto dinero tengo disponible**. |
| **Prioridad** | Alto |
| **Estimación** | |

### Tareas de HU-01 (Consultar saldo)

| Campo | Descripción |
|------|-------------|
| **ID** | TR-01 |
| **Título** | Diseñar servicio de consulta de saldo |
| **ID de la Historia de Uso asociada** | HU-01 |
| **Descripción** | Definir método/servicio para consultar saldo por número de cuenta (y/o por cliente autenticado). |
| **Tareas requisito** | — |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-02 |
| **Título** | Implementar lógica de negocio para consulta de saldo |
| **ID de la Historia de Uso asociada** | HU-01 |
| **Descripción** | Implementar validaciones mínimas y retornar saldo actual de la cuenta. |
| **Tareas requisito** | TR-01 |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-03 |
| **Título** | Pruebas unitarias de consulta de saldo |
| **ID de la Historia de Uso asociada** | HU-01 |
| **Descripción** | Crear pruebas para: cuenta válida, cuenta inexistente, cuenta inactiva, respuesta esperada. |
| **Tareas requisito** | TR-02 |

---

### HU-02
| Campo | Descripción |
|------|-------------|
| **ID** | HU-02 |
| **Título** | Realizar un depósito a una cuenta |
| **Descripción** | Como **cliente**, quiero **realizar un depósito a una cuenta**, para **agregar dinero de forma segura y controlada**. |
| **Prioridad** | Alto |
| **Estimación** |  |

### Tareas de HU-02 (Realizar depósito)

| Campo | Descripción |
|------|-------------|
| **ID** | TR-04 |
| **Título** | Diseñar flujo de depósito (entradas y validaciones) |
| **ID de la Historia de Uso asociada** | HU-02 |
| **Descripción** | Definir datos requeridos (cuenta destino, monto, origen/PSE simulado) y reglas de validación (monto > 0, cuenta activa). |
| **Tareas requisito** | — |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-05 |
| **Título** | Implementar interfaz de interracción con el usuario |
| **ID de la Historia de Uso asociada** | HU-02 |
| **Descripción** | Diseñar un a interfaz interactiva y facil de entendr para cualquier cliente |
| **Tareas requisito** | TR-04, TR-09 |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-06 |
| **Título** | Pruebas unitarias de depósito |
| **ID de la Historia de Uso asociada** | HU-02 |
| **Descripción** | Probar: depósito exitoso, monto inválido, cuenta inexistente/inactiva, límites básicos. |
| **Tareas requisito** | TR-05 |

---

### HU-03
| Campo | Descripción |
|------|-------------|
| **ID** | HU-03 |
| **Título** | Validar datos de cuenta antes de operar |
| **Descripción** | Como **cliente**, quiero **registrarme en la plataforma**, para **ejecutar operaciones y/o consultar mi cuenta**. |
| **Prioridad** | Medio |
| **Estimación** |  |

### Tareas de HU-03 (Validar cuenta antes de operar)

| Campo | Descripción |
|------|-------------|
| **ID** | TR-07 |
| **Título** | Implementar validación de formato de número de cuenta |
| **ID de la Historia de Uso asociada** | HU-03 |
| **Descripción** | Validar que el número de cuenta tenga 10 dígitos y solo números. |
| **Tareas requisito** | — |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-08 |
| **Título** | Validar banco registrado (prefijo de cuenta) |
| **ID de la Historia de Uso asociada** | HU-03 |
| **Descripción** | Verificar que los 2 primeros dígitos correspondan a un banco registrado en el sistema. |
| **Tareas requisito** | TR-07 |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-09 |
| **Título** | Validar estado de cuenta (activa/inactiva) |
| **ID de la Historia de Uso asociada** | HU-03 |
| **Descripción** | Bloquear consulta/depósito si la cuenta está inactiva. |
| **Tareas requisito** | TR-08 |

---

### HU-04
| Campo | Descripción |
|------|-------------|
| **ID** | HU-04 |
| **Título** | Confirmación y registro de transacciones |
| **Descripción** | Como **cliente**, quiero **recibir confirmación y que quede registro del depósito**, para **tener evidencia de la transacción**. |
| **Prioridad** |  |
| **Estimación** |  |


### Tareas de HU-04 (Confirmación y registro)

| Campo | Descripción |
|------|-------------|
| **ID** | TR-10 |
| **Título** | Definir estructura del registro de transacciones |
| **ID de la Historia de Uso asociada** | HU-04 |
| **Descripción** | Definir campos mínimos del registro: fecha/hora, cuenta, monto, estado, referencia. |
| **Tareas requisito** | — |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-11 |
| **Título** | Implementar guardado del registro del depósito |
| **ID de la Historia de Uso asociada** | HU-04 |
| **Descripción** | Guardar el registro cuando el depósito sea exitoso (o fallido con motivo). |
| **Tareas requisito** | TR-10, TR-05 |

| Campo | Descripción |
|------|-------------|
| **ID** | TR-12 |
| **Título** | Implementar confirmación al usuario (mensaje/respuesta) |
| **ID de la Historia de Uso asociada** | HU-04 |
| **Descripción** | Retornar confirmación con referencia y resumen del depósito. |
| **Tareas requisito** | TR-11 |

---
