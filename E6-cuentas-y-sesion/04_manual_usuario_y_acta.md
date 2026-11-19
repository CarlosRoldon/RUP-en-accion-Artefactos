ARTEFACTO 20 - MANUAL DE USUARIO Y ACTA DE ACEPTACION
Modulo: Cuentas de jugador y sesion | Duenos: Integrante 2 | Fase: Transicion

PARTE A - MANUAL DE USUARIO (RPG Manager, cuentas)

1. Registrarse
 Pantalla Crear cuenta (reemplazar por captura del prototipo):
 +------------------------------+
 |  RPG MANAGER - Crear cuenta  |
 |  Usuario:    [______________]|
 |  Correo:     [______________]|
 |  Contrasena: [______________]|
 |  [ Registrarme ]             |
 +------------------------------+
 a) Escribe un nombre de usuario que nadie mas use.  b) Escribe tu correo.  c) Elige una contrasena.  d) Pulsa Registrarme.  Si el usuario ya existe, el sistema te lo indica y debes elegir otro.

2. Iniciar sesion
 +------------------------------+
 |  RPG MANAGER - Iniciar sesion|
 |  Usuario:    [______________]|
 |  Contrasena: [______________]|
 |  [ Entrar ]  Olvide mi clave |
 +------------------------------+
 a) Escribe tu usuario y contrasena.  b) Pulsa Entrar y llegaras al menu principal.
 Importante: con 3 intentos fallidos seguidos tu cuenta se bloquea 15 minutos. Tu sesion se cierra sola tras 30 minutos sin actividad.

3. Recuperar contrasena
 +------------------------------+
 |  Recuperar contrasena        |
 |  Correo:     [______________]|
 |  [ Enviar enlace ]           |
 +------------------------------+
 a) En Iniciar sesion pulsa Olvide mi clave.  b) Escribe el correo con el que te registraste.  c) Abre el enlace que te llegara y define una contrasena nueva.

Nota de entrega: las capturas del prototipo (E3) sustituyen los esquemas de texto antes de exponer.

PARTE B - ACTA DE ACEPTACION
Proyecto: RPG Manager | Modulo: Cuentas de jugador y sesion | Version: 0.3 | Ambiente: pruebas

Criterio | Referencia | Resultado | Observaciones
AC-01 Iniciar sesion con credenciales validas | RF-CUE-02, CP-LOG-01 | Cumple | -
AC-02 Bloqueo a los 3 intentos fallidos | RF-CUE-03, RNF-CUE-02, CP-LOG-03 y 06 | Cumple | Tras corregir DEF-001
AC-03 El mensaje de error no revela que dato fallo | RNF-CUE-04, CP-LOG-05 | No cumple | DEF-002 abierto, severidad media
AC-04 El contador se reinicia tras acceso exitoso | RF-CUE-02, CP-LOG-04 | Cumple | Tras corregir DEF-003
AC-05 Despliegue en pruebas segun el plan | 03_plan_despliegue.md | Cumple | Prueba de humo exitosa
AC-06 Manual de usuario entregado | Parte A | Cumple | -

Decision: ACEPTADO CON OBSERVACIONES. DEF-002 se corrige en la siguiente iteracion. Registro y recuperacion de contrasena se aceptan en la siguiente iteracion, cuando se prueben.

Firma del cliente (profesor): ______________________  Fecha: ____________
Firma del equipo E6: ______________________ / ______________________
