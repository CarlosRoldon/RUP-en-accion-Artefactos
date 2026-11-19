ESLABON DE TRAZABILIDAD - E6 Cuentas de jugador y sesion

Como cada equipo trabaja un modulo distinto, aqui esta la version minima de los insumos que E6 necesita de las fases anteriores, hecha por nosotros para nuestro modulo. En un proyecto real cada uno lo produciria el rol indicado.

1. INSUMO DE E2 (Requisitos) - producido en realidad por el Especificador de requisitos

Requisitos funcionales
RF-CUE-01 | Registrar cuenta de jugador (usuario unico, correo, contrasena) | Alta
RF-CUE-02 | Iniciar sesion con usuario y contrasena | Alta
RF-CUE-03 | Bloquear la cuenta tras 3 intentos fallidos consecutivos | Alta
RF-CUE-04 | Recuperar contrasena con enlace enviado al correo | Media
RF-CUE-05 | Cerrar sesion | Media
RF-CUE-06 | Cerrar la sesion tras 30 minutos de inactividad | Baja

Requisitos no funcionales
RNF-CUE-01 | Seguridad: la contrasena se guarda con hash bcrypt, nunca en texto plano | Alta
RNF-CUE-02 | Seguridad: bloqueo exacto a los 3 intentos fallidos, duracion 15 minutos | Alta
RNF-CUE-03 | Rendimiento: el inicio de sesion responde en 2 segundos o menos con 100 usuarios concurrentes | Media
RNF-CUE-04 | Seguridad: el mensaje de error no revela si fallo el usuario o la contrasena | Media

Caso de uso Iniciar sesion (version corta)
- Actor: Jugador. Precondicion: cuenta registrada y no bloqueada.
- Flujo basico: 1) el jugador ingresa usuario y contrasena; 2) el sistema valida que no esten vacios; 3) compara el hash de la contrasena; 4) crea la sesion y reinicia el contador de intentos; 5) muestra el menu principal.
- A1 contrasena incorrecta: suma un intento y muestra mensaje generico.
- A2 tercer intento fallido: bloquea la cuenta 15 minutos.
- A3 cuenta bloqueada: rechaza el acceso aunque la contrasena sea correcta.
- Cubre: RF-CUE-02, RF-CUE-03, RNF-CUE-02, RNF-CUE-04.

2. INSUMO DE E4 (Arquitectura) - producido en realidad por el Arquitecto de software
- Arquitectura en 3 capas: vista web, servicio (AutenticacionService), persistencia (JugadorRepository).
- Despliegue: navegador del jugador, servidor de aplicacion Java 21, servidor MariaDB, servidor de correo SMTP.

3. INSUMO DE E5 (Construccion) - producido en realidad por el Implementador
- Componente de autenticacion con login(), logout() y recuperarContrasena(); script SQL con tablas jugador y sesion; version candidata 0.3.

4. A DONDE ALIMENTA NUESTRO TRABAJO
- Casos de prueba (01) -> Registro de defectos (02)
- Registro de defectos -> Plan de iteracion siguiente y codigo corregido (E5)
- Plan de despliegue (03) -> Manual y acta (04)
- Manual + resultados de prueba -> Acta de aceptacion -> Cierre del proyecto

5. CADENA DE TRAZABILIDAD DE NUESTRO MODULO
RF/RNF | Caso de uso | Caso de prueba | Defecto | Criterio de aceptacion
RF-CUE-02 | CU Iniciar sesion | CP-LOG-01, CP-LOG-02, CP-LOG-04 | DEF-003 | AC-01, AC-04
RF-CUE-03 + RNF-CUE-02 | CU Iniciar sesion (A2, A3) | CP-LOG-03, CP-LOG-06 | DEF-001 | AC-02
RNF-CUE-04 | CU Iniciar sesion (A1) | CP-LOG-02, CP-LOG-05 | DEF-002 | AC-03
Despliegue (SAD) | - | - | - | AC-05
Manual (prototipo) | - | - | - | AC-06
