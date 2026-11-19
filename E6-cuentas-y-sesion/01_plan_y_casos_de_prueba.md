ARTEFACTO 17 - PLAN Y CASOS DE PRUEBA
Modulo: Cuentas de jugador y sesion | Duenos: Julian David Oviedo | Fase: Elaboracion -> Construccion

PLAN DE PRUEBAS
- Alcance: caso de uso Iniciar sesion (RF-CUE-02, RF-CUE-03, RNF-CUE-02, RNF-CUE-04). Registro y recuperacion de contrasena se prueban en la siguiente iteracion.
- Tipos de prueba: funcional (caja negra) y de seguridad (bloqueo y mensajes).
- Ambiente: pruebas (ver 03_plan_despliegue.md), cuenta de prueba mago_elric / Dragon#2026.
- Responsable: disenador de pruebas (E6). Ejecuta: tester (E6).
- Criterio de salida: 100% de los casos ejecutados, 0 defectos de severidad critica o alta abiertos, y todo defecto medio con plan de correccion.

CASOS DE PRUEBA - Iniciar sesion
ID | RF/RNF que verifica | Precondicion | Datos | Pasos | Resultado esperado
CP-LOG-01 | RF-CUE-02 | Cuenta activa, intentos = 0 | mago_elric / Dragon#2026 | 1) Abrir pantalla Iniciar sesion 2) Ingresar datos 3) Pulsar Entrar | Acceso al menu principal, sesion creada, intentos = 0
CP-LOG-02 (negativo) | RF-CUE-02, RNF-CUE-04 | Cuenta activa, intentos = 0 | mago_elric / Dragon#2025 | Igual que CP-LOG-01 | Mensaje "Usuario o contrasena incorrectos", sin sesion, intentos = 1
CP-LOG-03 (negativo) | RF-CUE-03, RNF-CUE-02 | Cuenta activa, intentos = 0 | mago_elric / Dragon#2025 (3 veces seguidas) | Repetir 3 veces el intento con contrasena incorrecta | Al 3.er fallo la cuenta se bloquea 15 min y se muestra "Cuenta bloqueada. Intente de nuevo en 15 minutos"
CP-LOG-04 | RF-CUE-02 | Cuenta activa, intentos = 2 | mago_elric / Dragon#2026 | Ingresar credenciales correctas | Acceso al menu principal y intentos reiniciado a 0
CP-LOG-05 (negativo) | RNF-CUE-04 | Usuario no existe | heroe_fantasma / Cualquiera#1 | Ingresar datos y pulsar Entrar | El mismo mensaje generico de CP-LOG-02, sin revelar que el usuario no existe
CP-LOG-06 (negativo) | RF-CUE-03 | Cuenta bloqueada (resultado de CP-LOG-03) | mago_elric / Dragon#2026 | Ingresar credenciales correctas | Acceso rechazado con mensaje de bloqueo, sin sesion

Nota: cada caso nombra el RF/RNF que verifica; asi cada requisito es verificable y rastreable (ver 00_eslabon_trazabilidad.md).
