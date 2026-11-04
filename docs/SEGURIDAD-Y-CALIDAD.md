# Seguridad y calidad

Citoo se diseñó con seguridad desde el principio, y se verificó con pruebas sobre el sistema publicado usando negocios de prueba que se eliminaron al terminar cada corrida.

## Qué se verificó

| Área | Qué se comprobó | Resultado |
|---|---|---|
| **Doble reserva** | Dos reservas simultáneas para la misma profesional y horario | Solo una se acepta |
| **Reintentos** | Enviar dos veces la misma reserva | No se duplica la cita |
| **Aislamiento entre salones** | Usar servicios o personal de otro salón | Bloqueado |
| **Aislamiento entre clientas** | Una clienta intenta ver la cita de otra | No se expone |
| **Permisos por rol** | Un salón o una profesional intenta modificar citas ajenas | Bloqueado |
| **Permisos de equipo** | Una profesional intenta crear personal o editar el perfil | Bloqueado |
| **Personal inactivo** | Reservar con alguien dado de baja | No es posible |
| **Datos inválidos** | Fechas, horarios, nombres, teléfonos y notas incorrectos | Rechazados en el servidor |
| **Fallos de servicios** | Caída de almacenamiento, base de datos o correo | Respuestas seguras, sin detalles internos |
| **Pantallas móviles** | Teléfonos de 375 y 412 px de ancho | Sin desbordes |

## Principios

- **Validación siempre en el servidor**, nunca solo en la pantalla.
- **Cada acción comprueba quién la pide** y a qué salón pertenece.
- **Errores sin filtraciones:** el usuario ve un mensaje claro y el sistema no revela detalles internos.
- **Un fallo de correo no rompe una reserva** ya guardada.

> Por razones de seguridad y propiedad intelectual, los detalles de implementación no se publican en este repositorio.
