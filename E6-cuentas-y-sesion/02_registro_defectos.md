ARTEFACTO 18 - REGISTRO DE DEFECTOS Y RESULTADOS
Modulo: Cuentas de jugador y sesion | Duenos: Julian David Oviedo | Fase: Construccion

TABLA DE EJECUCION
Caso | Ronda 1: resultado obtenido | Ronda 1 | Ronda 2 (tras correcciones) | Defecto
CP-LOG-01 | Acceso correcto al menu principal | Paso | - | -
CP-LOG-02 | Mensaje generico, intentos = 1 | Paso | - | -
CP-LOG-03 | No bloqueo al 3.er fallo; permitio un 4.o intento | Fallo | Paso | DEF-001
CP-LOG-04 | Acceso correcto pero intentos quedo en 2 | Fallo | Paso | DEF-003
CP-LOG-05 | Mostro "El usuario no existe" | Fallo | Fallo | DEF-002
CP-LOG-06 | No ejecutable: depende de CP-LOG-03 | No ejecutado | Paso | -

Resumen: ronda 1 = 2 pasaron, 3 fallaron, 1 no ejecutado. Ronda 2 = 5 pasaron, 1 fallo.

DEFECTOS
DEF-001 | Severidad: Alta | Estado: Verificado
- Titulo: La cuenta se bloquea al 4.o intento y no al 3.o (viola RNF-CUE-02 y RF-CUE-03)
- Pasos para reproducir: 1) abrir Iniciar sesion 2) ingresar mago_elric con contrasena incorrecta 3 veces 3) intentar una 4.a vez
- Obtenido: el 4.o intento se procesa; esperado: la cuenta ya esta bloqueada desde el 3.o
- Caso que lo detecto: CP-LOG-03. Correccion: la comparacion del contador cambio de > 3 a >= 3. Verificado en ronda 2.

DEF-002 | Severidad: Media | Estado: Abierto
- Titulo: El mensaje revela que el usuario no existe (viola RNF-CUE-04)
- Pasos para reproducir: 1) abrir Iniciar sesion 2) ingresar heroe_fantasma / Cualquiera#1 3) pulsar Entrar
- Obtenido: "El usuario no existe"; esperado: "Usuario o contrasena incorrectos"
- Caso que lo detecto: CP-LOG-05. Decision: se corrige en la siguiente iteracion (ver acta).

DEF-003 | Severidad: Media | Estado: Verificado
- Titulo: El contador de intentos no se reinicia tras un acceso exitoso (RF-CUE-02, paso 4 del CU)
- Pasos para reproducir: 1) fallar 2 veces 2) iniciar sesion con datos correctos 3) consultar el contador de intentos
- Obtenido: intentos = 2; esperado: intentos = 0
- Caso que lo detecto: CP-LOG-04. Correccion: reiniciar el contador al crear la sesion. Verificado en ronda 2.

Flujo de estados: Abierto -> Corregido -> Verificado. Un defecto solo se cierra cuando el caso que lo detecto se re-ejecuta y pasa.
